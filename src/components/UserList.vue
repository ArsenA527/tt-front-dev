<template>
  <ul class="list-reset user__list">
    <UserItem
      v-for="(user) in users"
      :key="user.id"
      :user="user"
    />
  </ul>
</template>


<script>
import UserItem from '@/components/UserItem.vue';

export default {
  components: {
    UserItem
  },

  props: ['users'],
};
</script>

<style lang="scss">

</style>
