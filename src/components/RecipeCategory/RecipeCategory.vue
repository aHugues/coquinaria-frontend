<template>
    <div class="category-card-wrapper">
        <div class="category-card-content">
            <div class="category-card-name">
                Category
            </div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style>
.category-card-wrapper {
    border-radius: 5px;
    min-width: 400px;
    height: 500px;
    box-sizing: border-box;
    background-image: 
        linear-gradient(
            rgba(0, 0, 0, 0.6),
            rgba(0, 0, 0, 0.6)
        ),
        url("../../assets/categories/biscuit.png");
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
