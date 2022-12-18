<template>
  <section class="products-wrpper">
    <h3 class="headeProducts-title">All running shoes</h3>

    <div class="sneakers">
      <div class="box" v-for="product in products" :key="product.id">
        <button class="heart-icon" @click="favorite(product)">
          <img src="@/assets/images/heart.svg" alt="" v-if="!product.fav" />
          <img src="@/assets/images/hearlaev.svg" alt="" v-if="product.fav" />
        </button>

       

        <img class="nike-sneaker" :src="product.images" alt="" />
        <h5>{{ product.name }}</h5>
        <div class="boxButton">
          <div class="boxButton-price">
            <span>Price:</span>
            <b>{{ product.price }} $</b>
          </div>

          <div></div>
          <button class="save-icon" v-if="buttonClick === product.id">
            <img class="icon-save" src="@/assets/images/saveicon.svg" alt="" />
          </button>

          <button
            class="button-iconPlus"
            @click="send(true, product.id, product)"
            v-else
          >
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

  data() {
    return {
      buttonClick: true,
      heart: true,
      cards: [],
      saveCards: [],
      // card: this.products[0],
    };
  },

  methods: {
    favorite(prod) {
      console.log(prod);
      prod.fav = !prod.fav;
      // this.cards.push(id);
      // console.log(this.cards);
    },

    isfavorite(number) {
      console.log(number);

      // this.cards = [];
    },

    send(name, id, product,boo) {
      this.$emit("send", name);
      this.$emit("prices", product.price);
     
      
      let index = this.products.findIndex((todo) => {
        return todo.id === id;
      });
      this.buttonClick = ++index;
      console.log(++index);
      this.$emit("productscard", product);
    },
  },
  
  
};
</script>

<style scoped>
.save-icon {
  border: none;
  border-radius: 8px;
  height: 32px;
  width: 32px;
}
</style>