<template>
  <div class="recipes-list-wrapper">
    category: {{ category }}
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

<style>

</style>
