<template>
  <div id="app">
    <div class="navbar-wrapper">
      <NavBar></NavBar>
    </div>
    <div class="main-page-wrapper">
      <MainPage></MainPage>
    </div>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue';
import MainPage from './components/MainPage.vue';

export default {
  name: 'app',
  components: {
    NavBar,
    MainPage,
  },
};
</script>

<style lang="scss">
body {
  margin: 0;
}
#app {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: lightgrey;
}
.navbar-wrapper {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 100px;
}
.main-page-wrapper {
  position: absolute;
  top: 100px;
  left: 0;
  right: 0;
  bottom: 0;
}

</style>
