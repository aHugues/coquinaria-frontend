<template>
    <div id="main-page">
        <div class="categories-wrapper">
            <recipe-category></recipe-category>
            <recipe-category></recipe-category>
            <recipe-category></recipe-category>
            <recipe-category></recipe-category>
            <recipe-category></recipe-category>
            <recipe-category></recipe-category>
        </div>
    </div>
</template>

<script>
import RecipeCategory from './RecipeCategory/RecipeCategory.vue';

export default {
    name: "MainPage",
    components: {
        RecipeCategory,
    }
}
</script>

<style lang="scss">
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
    grid-template-columns: auto auto auto auto;
    // grid-template-rows: auto auto;
    gap: 20px;
}

@media only screen and (max-width: 1700px) {
    .categories-wrapper {
        grid-template-columns: auto auto auto;
    }

@media only screen and (max-width: 1300px) {
    .categories-wrapper {
        grid-template-columns: auto auto;
    }
}

@media only screen and (max-width: 900px) {
    .categories-wrapper {
        grid-template-columns: auto;
    }
}
}
</style>

