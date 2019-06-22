<template>
  <div class="vertical-navbar">
    <div class="vertical-navbar-content">
      <div class="vertical-navbar-title">
        Categories
        <vue-material-icon name="menu" :size="32"></vue-material-icon>
      </div>
      <vertical-nav-bar-category
        v-for="(category, index) in categories" :selected="category==selectedCategory"
        :category="category" :key="index">
      </vertical-nav-bar-category>
    </div>
  </div>
</template>

<script>
import VueMaterialIcon from 'vue-material-icon';
import VerticalNavBarCategory from './VerticalNavBarCategory.vue';

export default {
  name: 'VerticalNavBar',
  components: {
    VerticalNavBarCategory,
    VueMaterialIcon,
  },
  props: {
    categories: Array,
    selectedCategory: String,
  },
};
</script>

<style lang="scss">
.vertical-navbar {
  background-color: #FAFAFA;
  height: 100%;
  box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
  z-index: 99;
  box-sizing: border-box;
  padding: 20px;
}

.vertical-navbar-content {
  display: grid;
  grid-template-columns: auto;
  grid-row-gap: 20px;
}
</style>
