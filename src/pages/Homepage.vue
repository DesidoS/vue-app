<template>
  <main>
    <SectionWithHeaderSpacer>
      <Container>
        <ApartmentsFilterForm class="apartments-filter" @submit="filter" />
      </Container>
      <Container>
        <p v-if="!filteredApartments.length">Nothing found</p>
        <ApartmentsList v-else :items="filteredApartments" />
      </Container>
    </SectionWithHeaderSpacer>
  </main>
</template>

<script>
import ApartmentsFilterForm from "../components/apartment/ApartmentsFilterForm.vue";
import ApartmentsList from "../components/apartment/ApartmentsList.vue";
import apartments from "../components/apartment/apartments.js";
import Container from "../components/shared/Container.vue";
import SectionWithHeaderSpacer from "../components/shared/SectionWithHeaderSpacer";

export default {
  name: "App",
  components: {
    ApartmentsList,
    ApartmentsFilterForm,
    Container,
    SectionWithHeaderSpacer,
  },

  data() {
    return {
      apartments,
      text: "",
      filters: {
        city: "",
        price: 0,
      },
    };
  },

  computed: {
    filteredApartments() {
      return this.filterByCityName(this.filterByPrice(this.apartments));
    },
  },
  methods: {
    filter({ city, price }) {
      this.filters.city = city;
      this.filters.price = price;
    },
    filterByCityName(apartments) {
      if (!this.filters.city) return apartments;

      return apartments.filter((apartments) => {
        return apartments.location.city === this.filters.city;
      });
    },
    filterByPrice(apartments) {
      if (!this.filters.price) return apartments;

      return apartments.filter((apartments) => {
        return apartments.price >= this.filters.price;
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.apartments-filter {
  margin-bottom: 40px;
}
</style>
