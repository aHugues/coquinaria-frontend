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
import NavBar from './components/NavBar/NavBar.vue';
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
@import url('https://fonts.googleapis.com/css?family=Roboto:300,400,500,700&display=swap');
$navbar-height: 60px;
body {
  margin: 0;
  font-family: 'Roboto', sans-serif;
}
#app {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: #F5F5F5;
}
.navbar-wrapper {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: $navbar-height;
}
.main-page-wrapper {
  position: absolute;
  top: $navbar-height;
  left: 0;
  right: 0;
  bottom: 0;
}

</style>
