<template>
  <main class="my-orders-page">
    <SectionWithHeaderSpacer>
      <Container>
        <section class="my-orders-page__content">
          <MainTitle>Orders</MainTitle>
          <OrdersList :items="orders" />
        </section>
      </Container>
    </SectionWithHeaderSpacer>
  </main>
</template>

<script>
import Container from "../components/shared/Container";
import SectionWithHeaderSpacer from "../components/shared/SectionWithHeaderSpacer";
import MainTitle from "../components/shared/MainTitle";
import OrdersList from "../components/my-orders/OrdersList";
// import { getOrders } from "../services/order.service";

export default {
  name: "MyOrdersPage",
  components: {
    SectionWithHeaderSpacer,
    Container,
    MainTitle,
    OrdersList,
  },
  data() {
    return {
      orders: [
        {
          id: "5f689a2c09b16000e9a2f47b",
          apartment: {
            title: "Delectus et iste.",
            imgUrl: "/apartments/apartment-1.jpg",
            rating: 3,
            price: 1667,
            location: {
              city: "Dnipro",
            },
          },
        },
        {
          id: "5f689a2c09b16000e9a2f47d",
          apartment: {
            title: "Eaque suscipit incidunt.",
            imgUrl: "/apartments/apartment-2.jpg",
            price: 2740,
            location: {
              city: "Poltava",
            },
          },
        },
        {
          id: "5f689a2c09b16000e9a2f48a",
          apartment: {
            title:
              "Doloremque labore ullam molestiae quis quis eos consequatur.",
            imgUrl: "/apartments/apartment-3.jpg",
            price: 2153,
            location: {
              city: "Kharkiv",
            },
          },
        },
        {
          id: "5f689a2c09b16000e9a2f481",
          apartment: {
            title: "Dolor at inventore et voluptas omnis unde.",
            imgUrl: "/apartments/apartment-4.jpg",
            price: 3074,
            location: {
              city: "Poltava",
            },
          },
        },
      ],
    };
  },
  async created() {
    // try {
    //   const { data } = await getOrders();
    //   this.orders = data;
    // } catch (error) {
    //   this.$notify({
    //     type: "error",
    //     title: "Something went wrong",
    //     text: error.message,
    //   });
    // }
  },
};
</script>

<style lang="scss" scoped>
.my-orders-page {
  &__content {
    max-width: 730px;
    margin: 0 auto 100px;
  }
}
</style>
