<template>
  <div>
    <li class="user__item">
      <div class="user__image">
        <img src="" alt="">
      </div>
      <div class="user__info">
        <p class="user__name">Bret</p>
        <p class="user__mail">Sincere@april.biz</p>
      </div>
    </li>
    <li class="user__item">
      <div class="user__image">
        <img src="" alt="">
      </div>
      <div class="user__info">
        <p class="user__name">Antonette</p>
        <p class="user__mail">Shanna@melissa.tv</p>
      </div>
    </li>
  </div>
</template>


<script>
export default {
  data() {
    return {}
  }
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

    &__image {
      width: 70px;
      height: 70px;
      border-right: 1px solid #E0E0E0;
    }

    &__info {
      width: calc(100% - 70px);
      padding: 15px;
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
