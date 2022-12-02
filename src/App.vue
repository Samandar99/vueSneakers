<template>
  <section class="container">
    <Navbar />
    <Banner />
  </section>
  <Products :products="products" />
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Banner from "@/components/Banner.vue";
import Products from "@/components/Products.vue";
export default {
  components: {
    Navbar,
    Banner,
    Products,
  },

  data() {
    return {
      products: [
        {
          id: 1,
          name: "Nike Blazer Mid Suede Mens Sneakers",
          img: require("@/assets/images/image6.jpg"),
        },
        {
          id: 2,
          name: "Nike Blazer Mid Suede Nike Air Max 270",
          img: require("@/assets/images/image7.jpg"),
        },
        {
          id: 3,
          name: "X Aka Boku Future Rider Nike Blazer Mid",
          img: require("@/assets/images/image8.jpg"),
        },
        {
          id: 4,
          name: "X Aka Boku Future Under Armour Curry 8",
          img: require("@/assets/images/image9.jpg"),
        },
        {
          id: 5,
          name: "X Aka Boku Future Under Nike Kyrie 7",
          img: require("@/assets/images/image10.jpg"),
        },
        {
          id: 6,
          name: "X Aka Boku Future Jordan Air Jordan 11",
          img: require("@/assets/images/image11.jpg"),
        },
        {
          id: 7,
          name: "X Aka Boku Nike LeBron XVIII",
          img: require("@/assets/images/image12.jpg"),
        },
        {
          id: 8,
          name: "X Aka Boku Nike Lebron XVII",
          img: require("@/assets/images/image13.jpg"),
        },
        {
          id: 9,
          name: "X Aka Boku Nike Blazer Mid Suede",
          img: require("@/assets/images/image14.jpg"),
        },
      ],
    };
  },
};
</script>

<style>
.container {
  max-width: 100%;

  /* background: linear-gradient(
    129.86deg,
    #21e8c4 -20.42%,
    #179b93 -3.13%,
    #267b87 24.22%,
    #0f474f 72.75%
  ); */
}
</style>
