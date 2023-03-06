<template>
  <div :id="$style.app"></div>
    <ApartmentsList :items="apartment" />
</template>

<script>
import ApartmentsList from "./components/apartment/ApartmentsList.vue";
import apartment from "./components/apartment/apartments";

export default {
  name: "App",
  components: {
    ApartmentsList,
  },
  data() {
    return {
      apartment,
      // apartment: {
      //   id: 1,
      //   price: 1000,
      //   rating: 3.2,
      //   description:
      //     "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod",
      // },
    };
  },
};
</script>

<style module>
#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>

<!-- <h1>{{ title }}</h1>
    <Button @click="increment" type="submit" outlined>Click</Button>
    <DirectiveTest />
    <StarRating :rating="3.5" /> -->

<!-- import Button from "./components/Button.vue";
import DirectiveTest from "./components/DirectiveTest.vue";
import StarRating from "./components/StarRating.vue"; -->
<!-- 
 data() {
    return {
      amountClicked: 0,
    };
  },
  computed: {
    title() {
      return `Amounts of click ${this.amountClicked}`;
    },
  },
  methods: {
    increment() {
      this.amountClicked += 1;
    }, -->
