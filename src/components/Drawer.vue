<template>
  <div class="drawer-container" v-if="opens">
    <div class="header-drawer">
      <h3 class="drawer-title">Корзина</h3>
      <button class="drawer__back-icon2" @click="sens(!true)">
        <img src="@/assets/images/back.svg" alt="" />
      </button>
    </div>
    <div class="items">
      <div class="drawer-block">
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
      <div class="footer-drawer">
        <ul class="listsave">
          <li>
            <span>Total:</span>
            <div class="dotted"></div>
            <b>21 498 $</b>
          </li>
          <li>
            <span>Tax</span>
            <div class="dotted"></div>
            <b>1074 $</b>
          </li>
          <button class="greenButton">
            Checkout <img src="@/assets/images/arrow.svg" alt="" />
          </button>
        </ul>
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
  },
  data() {
    console.log(this.opens);
    console.log(this.cards);
    return {
      openDrawer: this.opens,
      isopen: true,
    };
  },
  methods: {
    sens(names) {
      this.$emit("sens", names);
    },
    deleProducts(carId) {
      this.$emit("dellCard",carId)
    },
  },
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
</style>