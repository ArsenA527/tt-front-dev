<template>
  <li class="user__item">
    <router-link
      class="btn-reset user__btn"
      :to="{name: 'user', params: {id: user.id}}"
    >
      <div class="user__image">
        <img
          src="@/img/image-big.png"
          alt=""
          width="100%"
          height="100%"
          objectFit="cover"
        >
      </div>
      <div class="user__info">
        <p class="user__name">{{ user.username }}</p>
        <p class="user__mail">{{ user.email }}</p>
      </div>
    </router-link>
  </li>
</template>


<script>
export default {
  data() {
    return {}
  },

  props: ['user'],
}
</script>

<style lang="scss">
  .user {
    &__item:not(:last-child) {
      margin-bottom: 18px;
    }

    &__item {
      display: flex;
      border-radius: 10px;
      box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.10);
    }

    &__item:hover .user__info,
    &__item:active .user__info {
      background: #E0E0E0;
    }

    &__btn {
      display: flex;
      width: 100%;
    }

    &__image {
      width: 70px;
      height: 70px;
      border-right: 1px solid #E0E0E0;
    }

    &__info {
      width: calc(100% - 70px);
      padding: 15px;
      text-align-last: left;
      font-size: 14px;
      background: #FFF;
    }

    &__name {
      margin-bottom: 5px;
      color: #333;
      font-weight: 600;
    }

    &__mail {
      color: #76787D;
    }
  }
</style>
