<template>
    <div id="main-page">
        <div v-if="category != ''" class="selected-category-wrapper" @click="onCloseCategory">
          <div v-on:click.stop class="selected-category-content">
            <recipes-list :category="category"></recipes-list>
          </div>
        </div>
        <div v-if="category == ''" class="categories-wrapper">
            <recipe-category
              v-for="(category, index) in categories"
              v-on:open-category="onOpenCategory"
              :categoryName="category" :key="index" :imageUrl="images[index]">
            </recipe-category>
        </div>
    </div>
</template>

<script>
import RecipeCategory from './RecipeCategory/RecipeCategory.vue';
import RecipesList from './Recipe/RecipesList.vue';

// TODO: programmatically get list of categories instead of hardcoded list
const categoriesList = [
  'Entries',
  'Meals',
  'Sauces',
  'Desserts',
  'Cakes',
  'Bakeries',
];
const imagesList = categoriesList.map(category => `/img/categories/${category.toLowerCase()}.png`);

const getCategories = () => ({
  categories: categoriesList,
  images: imagesList,
  category: '',
});

function onOpenCategory(category) {
  this.category = category;
}

function onCloseCategory() {
  this.category = '';
}

export default {
  name: 'MainPage',
  components: {
    RecipeCategory,
    RecipesList,
  },
  data: getCategories,
  methods: {
    onOpenCategory,
    onCloseCategory,
  },
};
</script>

<style lang="scss">

.selected-category-wrapper {
    width: 100%;
    height: 100%;
    margin: auto;
    box-sizing: border-box;
    padding-top: 1%;
    background-color: grey;
}

.selected-category-content {
  width: 90%;
  height: 95%;
  margin: auto;
  background-color: #E0E0E0;
  border-radius: 5px;

}

#main-page {
    height: 100%;
    width: 100%;
    background-color: #E0E0E0;
    overflow-y: auto;
}
.categories-wrapper {
    padding: 10px 20px;
    height: 100%;
    box-sizing: border-box;
    display: grid;
    grid-template-columns: repeat( auto-fit, minmax(400px, 1fr) );
    margin: auto;
    // grid-template-rows: auto auto;
    gap: 20px;
}

// @media only screen and (max-width: 1700px) {
//     .categories-wrapper {
//         grid-template-columns: auto auto auto;
//     }

// @media only screen and (max-width: 1300px) {
//     .categories-wrapper {
//         grid-template-columns: auto auto;
//     }
// }

@media only screen and (max-width: 900px) {
    .categories-wrapper {
        grid-template-columns: auto;
    }
}
// }
</style>
