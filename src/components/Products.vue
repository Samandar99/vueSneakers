<template>
  <section class="products-wrpper">
    <h3 class="headeProducts-title">All running shoes</h3>

    <div class="sneakers">
      <div class="box" v-for="product in products" :key="product.id">
        <button class="heart-icon">
          <img src="@/assets/images/heart.svg" alt="" />
        </button>
        <img class="nike-sneaker" :src="product.images" alt="" />
        <h5>{{ product.name }}</h5>
        <div class="boxButton">
          <div class="boxButton-price">
            <span>Price:</span>
            <b>{{ product.price }}</b>
          </div>
          <button class="button-iconPlus">
            <img
              class="icon_plus"
              src="@/assets/images/VectorPlus.svg"
              alt="Plus"
            />
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    products: {
      typeof: Array,
    },
  },
};
</script>

<style>
</style>