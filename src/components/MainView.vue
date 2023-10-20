<template>
  <div class="content">
    <div class="content__image">
      <img src="@/img/image-big.png" alt="">
    </div>
    <div class="content__info">
      <h3 class="content__info-name">Ervin Howell</h3>
      <p class="content__info-email">email: <span>Shanna@melissa.tv</span></p>
      <p class="content__info-phone">phone: <span>010-692-6593 x09125</span></p>
      <h3 class="content__info-about">О себе:</h3>
      <p class="content__info-about-text">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {};
  },
}
</script>

<style lang="scss">
  .content {
    display: flex;
    justify-content: space-between;
    width: 77%;
    height: 100%;
    padding: 30px;
    border-left: 1px solid #E0E0E0;

    &__image {
      margin-right: 60px;
    }

    &__info {
      font-size: 14px;
      color: #76787D;

      &-name, &-about  {
        margin-bottom: 10px;
        color: #000;
        font-size: 16px;
        font-weight: 600;
      }

      &-email {
        margin-bottom: 10px;
        color: #333;
        font-weight: 600;

        & span {
          font-weight: 400;
          color: #76787D;
        }
      }

      &-phone {
        margin-bottom: 20px;
        color: #333;
        font-weight: 600;

        & span {
          font-weight: 400;
          color: #76787D;
        }
      }

      &-about {
        margin-bottom: 25px;
      }
    }
  }
</style>
