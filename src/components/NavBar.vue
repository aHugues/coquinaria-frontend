<template>
    <div class="navbar">
        <NavElement></NavElement>
        <NavElement></NavElement>
    </div>
</template>

<script>
import NavElement from './NavElement.vue';

export default {
    name: "NavBar",
    components: {
        NavElement,
    }
}
</script>


<style lang="sass">
.navbar
    width: 100%
    height: 100%
    background-color: #388E3C
    padding: 20px
    box-sizing: border-box
    

</style>

