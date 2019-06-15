<template>
    <div class="category-card-wrapper" :style="backgroundStyle">
        <div class="category-card-content">
            <div class="category-card-name">
                {{ categoryName }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "RecipeCategory",
    props: {
        categoryName: String,
        imageUrl: String,
    },
    computed: {
        backgroundStyle: function () {
            return {
                backgroundImage: `
                linear-gradient(
                    rgba(0, 0, 0, 0.6),
                    rgba(0, 0, 0, 0.6)
                ),
                url("${this.imageUrl}")
            `};
        }
    }
}
</script>

<style>
.category-card-wrapper {
    border-radius: 5px;
    /* min-width: 400px; */
    height: 100%;
    box-sizing: border-box;
    background-repeat: no-repeat;
    background-size: cover;

}
.category-card-content {
    padding: 10px;
    height: 100%;
    box-sizing: border-box;
}
.category-card-name {
    position: relative;
    top: 20%;
    font-weight: bold;
    font-size: 30pt;
    margin: auto;
    text-align: center;
    color: #F5F5F5;
}

</style>
