<template>
  <div v-if="isVisible">
    <h1>DirectiveTest</h1>
    <ul>
      <template v-for="fruit in fruits" v-bind:key="fruit">
        <li>{{ fruit }}</li>
      </template>
    </ul>
    <ul>
      <template v-for="(car, key) in cars" v-bind:key="car.color">
        <li>{{ `${key} : ${car.color}` }}</li>
      </template>
    </ul>
  </div>
</template>

<script>
export default {
  name: "directive-test",
  data() {
    return {
      isVisible: true,
      fruits: ["apple", "banana", "cherry"],
      cars: {
        audi: {
          color: "red",
        },
        tesla: {
          color: "silver",
        },
      },
    };
  },
};
</script>

<style lang="scss" scoped></style>
