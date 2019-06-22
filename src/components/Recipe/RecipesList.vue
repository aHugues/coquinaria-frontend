<template>
  <div class="recipes-list-wrapper">
    <h2 class="recipes-list-title">
      {{ category }}
    </h2>
  </div>
</template>

<script>
export default {
  name: 'RecipesList',
  props: {
    recipes: Array,
    category: String,
  },
};
</script>

<style lang="scss" scoped>
.recipes-list-wrapper {
  overflow: auto;
}

</style>
