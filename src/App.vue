<template>
  <section class="container">
    <Navbar />
    <Banner />
  </section>
  <Products />
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
