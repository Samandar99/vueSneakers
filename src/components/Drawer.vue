<template>
  <div class="drawer-container" v-if="opens">
    <div class="header-drawer">
      <h3 class="drawer-title">Корзина</h3>
      <button class="drawer__back-icon2" @click="sens(!true)">
        <img src="@/assets/images/back.svg" alt="" />
      </button>
    </div>
    <div class="items" v-if="cards.length === 0 ? false : true">
      <div class="drawer-block" v-if="orderProducts">
        <div class="boxs" v-for="(car, index) in cards" :key="index">
          <div>
            <img class="boxs-img" :src="car.images" alt="" />
          </div>
          <div class="boxes__alltext">
            <p class="text-sneaker__name">
              {{ car.name }}
            </p>
            <b>{{ car.price }}</b>
          </div>
          <button class="drawer__back-icon" @click="deleProducts(car.id)">
            <img src="@/assets/images/back.svg" alt="" />
          </button>
        </div>
      </div>
      <div class="footer-drawer" v-if="orderProducts">
        <ul class="listsave">
          <li>
            <span>Total:</span>
            <div class="dotted"></div>
            <b>
              {{ totalPrice }}
            </b>
          </li>
          <li>
            <span>Tax</span>
            <div class="dotted"></div>
            <b>1074 $</b>
          </li>
          <button class="greenButton" @click="orderProducts = false">
            Checkout <img src="@/assets/images/arrow.svg" alt="" />
          </button>
        </ul>
      </div>
      <div v-else class="container-order">
        <img class="order-icon" src="@/assets/images/orders.svg" alt="" />
        <h3 class="title-order">Order is processed!</h3>
        <p class="order-text">
          Your order #18 will be delivered to courier soon
        </p>
        <button class="order-button">
          <img class="arrowleft" src="@/assets/images/arrowleft.svg" alt="" />
          come back
        </button>
      </div>
    </div>

    <div v-else class="empty-container">
      <div class="block_empty">
        <img class="korzina" src="@/assets/images/cart.svg" alt="" />
        <h3>Cart is empty</h3>
        <p>Add at least one pair of sneakers to place an order.</p>
        <button class="back__button">
          <img class="arrowleft" src="@/assets/images/arrowleft.svg" alt="" />
          come back
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    opens: {
      typeof: Boolean,
    },
    cards: {
      typeof: Array,
    },
    totalPrice: {
      typeof: Number,
      default: 0,
    },
  },
  data() {
    console.log(this.opens);
    return {
      openDrawer: this.opens,
      isopen: true,
      orderProducts: true,
    };
  },
  methods: {
    sens(names) {
      this.$emit("sens", names);
    },
    deleProducts(carId) {
      this.$emit("dellCard", carId);
      console.log(this.cards.length);
    },
  },
  computed: {},
};
</script>

<style scoped>
.items {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 85%;
  position: fixed;
  overflow: auto;
}

.header-drawer {
  display: flex;
  justify-content: space-between;
  margin-bottom: 30px;
}
.drawer-container {
  position: fixed;
  right: 0;
  width: 420px;
  max-width: 100%;
  height: 100%;
  background: #fff;
  box-shadow: -10px 4px 24px rgba(0, 0, 0, 0.1);
  padding: 30px;
  z-index: 9;
}

.drawer-title {
  font-family: "Inter";
  font-size: 24px;
}
.boxs {
  border: 1px solid #f3f3f3;
  border-radius: 20px;
  display: flex;
  margin-bottom: 20px;
  align-items: center;
  padding: 20px 20px;
}

.boxs-img {
  width: 70px;
  height: 70px;
  object-fit: contain;
  background-position: 0 -3px;
  background-repeat: no-repeat;
}

.drawer__back-icon {
  background: none;
  border: none;
  cursor: pointer;
  margin-left: 20px;
}

.drawer__back-icon2 {
  background: none;
  border: none;
  cursor: pointer;
}

.text-sneaker__name {
  width: 160px;
  line-height: 17px;
  margin-bottom: 8px;
  font-size: 14px;
  margin-right: 10px;
  font-family: "RR";
  font-style: normal;
  font-weight: 400;
}
.boxes__alltext {
  margin-left: 21px;
}

.listsave {
  margin-bottom: 0px;
}
.listsave li {
  display: flex;
  align-items: flex-end;
  margin-bottom: 20px;
}
.dotted {
  flex: 1;
  height: 1px;
  border-bottom: 1px dashed #dfdfdf;
  position: relative;
  top: -4px;
  margin: 0 7px;
}

.greenButton {
  position: relative;

  width: 100%;
  height: 55px;
  background: #9dd558;
  border-radius: 18px;
  border: none;
  color: #fff;
  font-size: 16px;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
}

.greenButton img {
  position: absolute;
  right: 30px;
  top: 20px;
  transition: transform 0.2s ease-in-out;
}

.greenButton img:hover {
  transform: translateX(5px);
}
.greenButton:hover {
  background: #77d703;
}

.empty-container {
  width: 300px;
  height: 90vh;
  /* background: #9dd558; */
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: auto;
}

.block_empty {
  text-align: center;
  width: 300px;
  height: 300px;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.korzina {
  width: 120px;
  height: 120px;
  object-fit: cover;
  margin-bottom: 21px;
}

.block_empty p {
  margin-top: 8px;
}
.block_empty button {
  margin-top: 40px;
  padding: 20px 90px;
  border-radius: 18px;
  border: none;
  display: flex;
  gap: 20px;
  align-items: center;
  background: #9dd458;
  color: #fff;
  cursor: pointer;
}

.container-order {
  width: 100%;

  display: flex;
  flex-direction: column;
  align-items: center;
  margin: auto;
}

.order-icon {
  width: 83px;
  height: 120px;
  object-fit: cover;
}
.order-button {
  margin-top: 40px;
  padding: 20px 90px;
  border-radius: 18px;
  border: none;
  display: flex;
  gap: 20px;
  align-items: center;
  background: #9dd458;
  color: #fff;
  cursor: pointer;
}
.title-order {
  margin-top: 2rem;
}

/* media */

@media (max-width: 766px) {
  .drawer-container {
    position: fixed;
    right: 0;
    width: 60%;
    max-width: 100%;
    height: 100%;
    background: #fff;
    box-shadow: -10px 4px 24px rgba(0, 0, 0, 0.1);
    padding: 0px 100px 100px 0px;
    z-index: 9;
  }

  .items {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    width: 220px;
    height: 85%;
    position: fixed;
    overflow: auto;
    gap: 30px;
    padding: 0px 50px 0px 10px;
  }
  .boxs {
    border: 1px solid #f3f3f3;
    border-radius: 20px;
    display: flex;
    flex-direction: column;
    margin-bottom: 0px;
    width: 100%;
    padding: 0px 0px;
  }
  .header-drawer {
  display: flex;
  justify-content: space-between;
  gap: 20px;
  margin-bottom: 30px;
  margin-top: 100px;
  margin-left: 2rem;
}
}
</style>