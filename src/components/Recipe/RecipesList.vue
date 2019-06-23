<template>
  <div class="recipes-list-wrapper">
    <div class="recipes-list-title-wrapper card" :class="{'full-size': menuButton}">
      <transition name="fade">
        <div v-if="menuButton" class="menu-button" @click="$emit('open-vertical-navbar')">
          <vue-material-icon name="menu" :size="32"></vue-material-icon>
        </div>
      </transition>
      <h2 class="recipes-list-title">{{ category }} recipes</h2>
    </div>
    <div class="recipes-list">
      <div class="card recipe" v-for="(recipe, index) in recipes" :key="index">
        <div class="recipe-time">
          <div class="circle" :style="{backgroundColor: getColor(recipe.duration)}">
            {{ recipe.duration }}'
            </div>
        </div>
        <div class="recipe-title">
          {{ recipe.name }}
        </div>
        <div class="recipe-description">
          {{ recipe.description }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VueMaterialIcon from 'vue-material-icon';

function getColor(time) {
  if (time < 30) {
    return '#00838F';
  }
  if (time < 60) {
    return '#1565C0';
  }
  return '#4527A0';
}

export default {
  name: 'RecipesList',
  props: {
    recipes: Array,
    category: String,
    menuButton: Boolean,
  },
  methods: {
    getColor,
  },
  components: {
    VueMaterialIcon,
  }
};
</script>

<style lang="scss" scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}

.recipes-list-wrapper {
  padding: 10px;
  height: 100%;
}

.recipes-list-title {
  margin: 0;
  font-weight: 600;
  grid-column-start: 2;
}

.recipes-list-title-wrapper {
  display: grid;
  grid-template-columns: 0px auto;
  grid-template-rows: 40px;
  transition: grid-template-columns 0.3s;
  align-items: center;
  margin-bottom: 10px;
  height: 8%;
}

.full-size {
  grid-template-columns: 50px auto;
  .menu-button {
    cursor: pointer;
  }
}

.circle {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #757575;
  line-height: 40px;
  text-align: center;
  color: #FAFAFA;

}

.recipe {
  display: grid;
  grid-template-columns: 50px auto;
  row-gap: 5px;
  column-gap: 5px;
  align-items: center;
  width: 100%;
}

.recipe-title {
  font-size: 16pt;
  font-weight: 500;
  box-sizing: border-box;
}

.recipe-time {
  grid-row: 1 / span 2;
}

.recipe-description {
  grid-column-start: 2;
  color: #212121;
}

.recipes-list {
  overflow-x: auto;
  display: grid;
  grid-template-columns: auto;
  row-gap: 10px;
  z-index: 90;
  // width: 100%;
  height: 88%;
}

.card {
  padding: 20px;
  background-color: #F5F5F5;
  box-sizing: border-box;
  box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
  &.recipe {
    z-index: 95;
  }
}

</style>
