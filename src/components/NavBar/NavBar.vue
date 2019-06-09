<template>
    <div class="navbar">
        <NavTitle></NavTitle>
        <NavElement></NavElement>
        <NavElement></NavElement>
    </div>
</template>

<script>
import NavElement from './NavElement.vue';
import NavTitle from './NavTitle.vue';

export default {
    name: "NavBar",
    components: {
        NavElement,
        NavTitle,
    }
}
</script>


<style lang="scss">
.navbar {
    width: 100%;
    height: 100%;
    background-color: #388E3C;
    padding: 20px;
    box-sizing: border-box;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
}

</style>

