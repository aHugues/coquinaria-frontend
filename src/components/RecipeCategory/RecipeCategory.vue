<template>
    <div class="category-card-wrapper"
        :style="backgroundStyleBase"
        @mouseover="hover = true" @mouseleave="hover = false">
      <div class="category-card-overlay" :class="{ hover: hover}">
        <div class="category-card-content">
            <h3 class="category-card-name" :class="{ hover: hover}">
                {{ categoryName }}
            </h3>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'RecipeCategory',
  props: {
    categoryName: String,
    imageUrl: String,
  },
  data() {
    return {
      hover: false,
    };
  },
  computed: {
    backgroundStyleBase() {
      return {
        backgroundImage: `url("${this.imageUrl}")`,
      };
    },
  },
};
</script>

<style lang="scss">

.category-card-overlay {
  background-image: linear-gradient(
    rgba(0, 0, 0, 0.6),
    rgba(0, 0, 0, 0.6)
  );
  border-radius: 5px;
  height: 100%;
  opacity: 0;
  transition: opacity 0.5s;
  &.hover {
    opacity: 1;
  }
}

.category-card-wrapper {
    border-radius: 5px;
    /* min-width: 400px; */
    height: 100%;
    box-sizing: border-box;
    background-repeat: no-repeat;
    background-size: cover;
    transition: background-image 0.5s;
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
    font-size: 4vw;
    margin: auto;
    text-align: center;
    color: #F5F5F5;
    opacity: 0;
    transition: opacity 0.3s;
    &.hover {
      opacity: 1;
    }
}

</style>
