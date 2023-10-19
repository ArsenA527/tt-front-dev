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
    <UserList
      :users="users"
    />
  </aside>
</template>

<script>
import UserList from '@/components/UserList.vue';

export default {

  data() {
    return {
      searchUsers: '',

      usersData: null,
      usersLoading: false,
      usersLoadingFailed: false,
    }
  },
  components: { UserList },

  computed: {
    users() {
      return [];
    }
  },

  methods: {
    loadUsers(event) {
      this.usersLoading = true;
      this.usersLoadingFailed = false;
      clearTimeout(this.loadUsersTimer);
      this.loadUsersTimer = setTimeout(() => {
        this.searchUsers = event.target.value;
        console.log('axios');
        console.log(this.searchUsers);
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
