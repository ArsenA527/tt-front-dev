<template>
  <aside class="aside">
    <p class="aside__title">
      Поиск сотрудников
    </p>
    <label class="aside__label">
      <input
        type="text"
        class="input-reset aside__input"
        v-bind:value="searchUsers"
        @input="loadUsers"
      >
    </label>
    <p class="aside__title">
      Результаты
    </p>
    <div v-if="usersLoading">Идет поиск ...</div>
    <div v-if="usersLoadingFailed">Нет данных</div>
    <div v-if="users">
      <UserList
        :users="users"
      />
    </div>

  </aside>
</template>

<script>
import axios from 'axios';
import { API_BASE_URL } from '@/config';
import UserList from '@/components/UserList.vue';
import Loader from './Loader.vue';

export default {

  data() {
    return {
      searchUsers: '',

      usersData: null,
      usersLoading: false,
      usersLoadingFailed: false,
    }
  },
  components: { UserList, Loader },

  computed: {
    users() {
      return this.usersData ? this.usersData : [];
    }
  },

  methods: {
    loadUsers(event) {
      this.usersLoading = true;
      this.usersLoadingFailed = false;
      clearTimeout(this.loadUsersTimer);
      this.loadUsersTimer = setTimeout(() => {
        this.searchUsers = event.target.value;
        axios.get(API_BASE_URL + '/users')
          .then((response) => {
            if (this.searchUsers) {
              this.usersData = response.data.filter(user => {
                return user.username.toLowerCase().indexOf(this.searchUsers.toLowerCase()) !== -1
                  || user.name.toLowerCase().indexOf(this.searchUsers.toLowerCase()) !== -1
                  || user.id == this.searchUsers;
              })
            }
          })
          .catch(() => this.usersLoadingFailed = true)
          .then(() => this.usersLoading = false);
      }, 2000)
    },

  }
}
</script>


<style lang="scss">
  .aside {
    padding: 27px 31px 27px 20px;
    width: calc(100% - 975px);
    background: #FDFDFD;

    &__title {
      margin-bottom: 22px;
      font-size: 16px;
      font-weight: 600;
    }

    &__label {
      display: block;
      max-height: 46px;
      margin-bottom: 22px;
    }

    &__input {
      padding: 16px;
      width: 240px;
      border-radius: 8px;
      border: 1.5px solid #E9ECEF;
      background: #FFF;
      color: #76787D;
      font-size: 14px;
    }

  }

</style>
