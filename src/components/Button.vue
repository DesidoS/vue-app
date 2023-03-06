<template>
  <button v-bind:type="type" :class="{ btn: true, 'btn--outlined': outlined }">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "general-button",
  props: {
    type: {
      type: String,
      default: "button",
    },
    outlined: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style lang="scss" scoped>
.btn {
  width: 350px;
  height: 50px;
  background: #ff662d;
  cursor: pointer;
  border: 0;
  color: #fff;
  &:hover {
    opacity: 0.5;
    border: 1px solid black;
    transition: opacity 250ms cubic-bezier(0.4, 0, 0.2, 1),
      border 250ms cubic-bezier(0.4, 0, 0.2, 1);
  }
  &--outlined {
    background: #fff;
    color: #000;
    border: 2px solid #ff662d;
    &:hover {
      background: #ff662d;
      border: 1px solid black;
      transition: background 250ms cubic-bezier(0.4, 0, 0.2, 1),
        border 250ms cubic-bezier(0.4, 0, 0.2, 1);
    }
  }
}
</style>
