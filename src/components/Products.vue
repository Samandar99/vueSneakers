<template>
  <section class="products-wrpper">
    <h3 class="headeProducts-title">All running shoes</h3>

    <div class="sneakers">
      <div class="box" v-for="product in products" :key="product.id">
        <button class="heart-icon" @click="favorite(product.id)">
          <img src="@/assets/images/heart.svg" alt="" />
        </button>

        <div
          v-for="(card, index) in cards"
          :key="index"
          @click="isfavorite(card)"
        >
          <button class="heart-icon" v-if="card === product.id">
            <img src="@/assets/images/hearlaev.svg" alt="" />
          </button>
        </div>

        <img class="nike-sneaker" :src="product.images" alt="" />
        <h5>{{ product.name }}</h5>
        <div class="boxButton">
          <div class="boxButton-price">
            <span>Price:</span>
            <b>{{ product.price }}</b>
          </div>

          <button class="save-icon" v-if="buttonClick === product.id">
            <img class="icon-save" src="@/assets/images/saveicon.svg" alt="" />
          </button>

          <button
            class="button-iconPlus"
            @click="send(true, product.id)"
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
      // card: this.products[0],
    };
  },

  methods: {
    favorite(id) {
      this.cards.push(id);
      console.log(this.cards);
    },
    isfavorite(number) {
      // console.log(number);

      let dupChars = this.cards.filter((element, index) => {
        return this.cards.indexOf(element) !== index;
      });
      this.cards = dupChars;
      
      console.log(dupChars);
    },

    send(name, id) {
      console.log(name);
      this.$emit("send", name);
      let index = this.products.findIndex((todo) => {
        return todo.id === id;
      });
      this.buttonClick = ++index;
      console.log(++index);
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