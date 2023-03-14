<template>
    <Container>
      <!-- <slot name="title"></slot> -->
    <div class="apartments-list">
      <ApartmentsItem
        v-for="{ id, descr, price, rating, imgUrl } in items"
        :key="id"
        :id="id"
        :descr="descr"
        :price="price"
        :rating="rating"
        :imgUrl="imgUrl"
      />
    </div>
  </Container>
        <!-- <template v-for="apartment in items">
            <slot name="apartment" v-bind:apartment="apartment"></slot> -->
</template>

<script>
import Container from "../shared/Container";
import ApartmentsItem from "./ApartmentsItem.vue";

export default {
  name: "ApartmentsList",
  components: {
    Container,
    ApartmentsItem,
  },
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style lang="scss" scoped>
.apartments-list {
  display: flex;
  flex-wrap: wrap;
  margin-left: -15px;
  margin-right: -15px;
}
</style>
