<template>
  <div class="recipes-list-wrapper">
    <h2 class="recipes-list-title card">
      {{ category }} recipes
    </h2>
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
  },
  methods: {
    getColor,
  },
};
</script>

<style lang="scss" scoped>
.recipes-list-wrapper {
  padding: 10px;
}

.recipes-list-title {
  margin: 0;
  margin-bottom: 10px;
  font-weight: 600;
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
  overflow: auto;
  display: grid;
  grid-template-columns: auto;
  row-gap: 10px;
}

.card {
  padding: 20px;
  background-color: #F5F5F5;
  box-sizing: border-box;
  box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
}

</style>
