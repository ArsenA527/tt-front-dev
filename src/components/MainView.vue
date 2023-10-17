<template>
  <div class="content">
    <UserItem />
  </div>
</template>

<script>
import UserItem from './UserItem.vue';

export default {
    data() {
      return {};
    },
    components: { UserItem }
}
</script>

<style lang="scss">
  .content {
    width: 77%;
  }
</style>
