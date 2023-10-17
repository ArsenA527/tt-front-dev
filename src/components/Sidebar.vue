<template>
  <aside class="aside">
    <p class="aside__title">
      Поиск сотрудников
    </p>
    <label class="aside__label">
      <input type="text" class="input-reset aside__input">
    </label>
    <p class="aside__title">
      Результаты
    </p>
    <ul>

    </ul>
  </aside>
</template>

<script>


export default {
  data() {
    return {}
  }
}
</script>


<style lang="scss">
  .aside {
    width: calc(100% - 975px);

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
