<template>
    <div id="main-page">
        <div v-if="category != ''" class="selected-category-wrapper" @v-on:close-category="onCloseCategory">
          <!-- <div v-on:click.stop class="selected-category-content"> -->
            <div class="vertical-navbar-wrapper" :class="{ closed: verticalNavbarClosed }">
              <vertical-nav-bar :categories="categories" :selectedCategory="category" @close-vertical-navbar="verticalNavbarClosed = true">
              </vertical-nav-bar>
            </div>
            <div class="recipes-category-wrapper" :class="{'full-page': verticalNavbarClosed}">
              <recipes-list :category="category"></recipes-list>
            </div>
          <!-- </div> -->
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
import VerticalNavBar from './VerticalNavBar/VerticalNavBar.vue';

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
  verticalNavbarClosed: false,
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
    VerticalNavBar,
  },
  data: getCategories,
  methods: {
    onOpenCategory,
    onCloseCategory,
  },
};
</script>

<style lang="scss">

$vertical-navbar-width: 300px;

.closed {
  width: 0px !important;
}

.full-page {
  left: 0 !important;
}

.selected-category-wrapper {
    width: 100%;
    height: 100%;
    background-color: #E0E0E0;
    box-sizing: border-box;
    z-index: 10;
}

.vertical-navbar-wrapper {
  width: $vertical-navbar-width;
  transition: width 0.3s;
  position: absolute;
  top: 0;
  bottom: 0;
  z-index: 98;
  overflow: hidden;
}

.recipes-category-wrapper {
  position: absolute;
  top: 0;
  left: $vertical-navbar-width;
  right: 0;
  bottom: 0;
  transition: left 0.3s;
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
