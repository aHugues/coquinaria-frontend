<template>
  <div class="vertical-navbar">
    <div class="vertical-navbar-content">
      <div class="vertical-navbar-title">
        <span class="vertical-navbar-title-content">Categories</span>
        <span class="spacer-3"></span>
        <span class="clickable" @click="$emit('close-vertical-navbar')">
          <vue-material-icon name="chevron_left" :size="32"></vue-material-icon>
        </span>
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
  z-index: 99;
  box-sizing: border-box;
  padding: 20px;
}

.vertical-navbar-content {
  display: grid;
  grid-template-columns: auto;
  grid-row-gap: 20px;
}

.spacer-3 {
  flex: 3;
}

.clickable {
  cursor: pointer;
}

.vertical-navbar-title {
  display: flex;
  align-items: center;

  .vertical-navbar-title-content {
    padding: 10px;
    box-sizing: border-box;
    font-weight: 500;
    font-size: 16pt;
  }
}
</style>
