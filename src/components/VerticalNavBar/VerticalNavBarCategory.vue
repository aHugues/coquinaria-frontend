<template>
  <div class="vertical-navbar-category" :class="{selected: selected}"
    @click="$emit('change-category', category)">
    {{ category }}
  </div>
</template>

<script>
export default {
  name: 'vertical-navbar-category',
  props: {
    category: String,
    selected: Boolean,
  },

};
</script>

<style lang="scss">
.vertical-navbar-category {
  box-sizing: border-box;
  padding: 10px;
  background-color: none;
  transition: background-color 0.3s;
  cursor: pointer;

  &:hover {
    background-color: #A5D6A7;
  }

  &.selected {
    background-color: #66BB6A;
  }
}

</style>
