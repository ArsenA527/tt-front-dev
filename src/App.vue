<template>
  <div class="container">
    <header class="header">
      <div class="header__wrapper">
        <h2 class="header__heading">Жилфонд</h2>
        <p class="header__user">Пользователь</p>
      </div>
    </header>

    <main class="main">
      <Sidebar />
      <MainView />
    </main>
  </div>
</template>

<script>
import MainView from '@/components/MainView.vue';
import Sidebar from '@/components/Sidebar.vue';

export default {
  name: 'App',
  components: {
    Sidebar,
    MainView
  },

  data() {
    return {}
  }
}
</script>

<style lang="scss">

.header {
  margin-bottom: 40px;

  &__wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__heading {
    font-size: 32px;
    font-weight: 700;
    color: #E31F24;
  }

  &__user {
    font-size: 16px;
  }

}
</style>
