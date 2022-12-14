<template>
  <Drawer :opens="opens" @sens="getr1" :cards="cards" @dellCard="getdell" />
  <Header />
  <Products :products="products" @send="get" @productscard="getcard" />
  <About />
  <Subescribe />
  <Footer />
</template>

<script>
import Header from "@/components/Header.vue";
import Products from "@/components/Products.vue";
import About from "@/components/About.vue";
import Subescribe from "@/components/Subescribe.vue";
import Footer from "@/components/Footer.vue";
import Drawer from "@/components/Drawer.vue";

export default {
  components: {
    Drawer,
    Header,
    Products,
    About,
    Subescribe,
    Footer,
  },

  data() {
    return {
      products: [
        {
          id: 1,
          name: "Nike Blazer Mid Suede Mens Sneakers",
          price: "12 999",
          images: require("@/assets/images/image1.png"),
          cart: null,
          fav: false,
        },

        {
          id: 2,
          name: "Nike Blazer Mid Nike Air Max 270",
          price: "12 999",
          images: require("@/assets/images/image7.jpg"),
          cart: null
        },

        {
          id: 3,
          name: "Nike Blazer Puma X Aka Boku Future Rider",
          price: "8 499",
          images: require("@/assets/images/image8.jpg"),
          cart: null
        },

        {
          id: 4,
          name: "Nike Blazer Puma X Aka Boku Future Rider",
          price: "8 499",
          images: require("@/assets/images/image9.jpg"),
          cart: null
        },
        {
          id: 5,
          name: "Nike Blazer Кроссовки Nike Kyrie 7",
          price: "11 299",
          images: require("@/assets/images/image10.jpg"),
          cart: null
        },
        {
          id: 6,
          name: "Men's Nike Kyrie Flytrap IV",
          price: "13 999",
          images: require("@/assets/images/image11.jpg"),
          cart: null
        },

        {
          id: 7,
          name: "Men's Puma X Aka Boku Future Rider",
          price: "8 999",
          images: require("@/assets/images/image12.jpg"),
          cart: null
        },
        {
          id: 8,
          name: "Men's Nike Kyrie Flytrap IV",
          price: "8 999",
          images: require("@/assets/images/image13.jpg"),
          cart: null
        },
        {
          id: 9,
          name: "Men's Jordan Air Jordan 11",
          price: "16 499",
          images: require("@/assets/images/image14.jpg"),
          cart: null
        },
      ],
      opens: false,
      cards: [],
    };
  },
  methods: {
    get(name) {
      this.opens = name;
    },
    getr1(names) {
      this.opens = names;
    },
    getcard(product) {
      this.cards.push(product);
      console.log(this.cards);
    },
    getdell(carId) {
      let cardsIndex = this.cards.findIndex((goods) => goods.id === carId);
      this.cards.splice(cardsIndex, 1);
    },
  },
};
</script>

<style>
</style>
