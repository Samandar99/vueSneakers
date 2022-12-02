<template>
  <section class="products-wrpper">
    <h1 class="headeProducts-title">All running shoes</h1>

    <div class="sneakers">
      <div class="box" v-for="(product, index) in products" :key="index">
        <button class="heart-icon">
          <img src="@/assets/images/heart.svg" alt="" />
        </button>
        <img class="nike-sneaker" :src="product.img" alt="" />
        <h5>{{product.name}}</h5>
        <div class="boxButton">
          <div class="boxButton-price">
            <span>Price:</span>
            <b>12 999 $.</b>
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

<style scoped>
.products-wrpper {
  max-width: 1000px;
  width: 100%;
  height: 600px;
  margin: auto;
}

.sneakers {
  display: flex;
  gap: 30px;
  flex-wrap: wrap;
}
.box {
  border: 1px solid #f3f3f3;
  padding: 30px;
  width: 220px;
  border-radius: 40px;
  transition: all 0.3s ease-out;
  display: flex;
  flex-direction: column;
  position: relative;
}

.box:hover {
  box-shadow: rgba(0, 0, 0, 0.1) 0px 20px 25px -5px,
    rgba(0, 0, 0, 0.04) 0px 10px 10px -5px;
}

.boxButton {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.boxButton-price {
  display: flex;
  flex-direction: column;
  margin-top: 12px;
}

.icon_plus {
  width: 11px;
  height: 11px;
}

.nike-sneaker {
  width: 133px;
  height: 112px;
  object-fit: cover;
}
.button-iconPlus {
  background: #fff;
  border: 1px solid #f2f2f2;
  box-sizing: border-box;
  border-radius: 8px;
  height: 32px;
  width: 32px;
  cursor: pointer;
}

h5 {
  font-weight: 400;
  font-size: 14px;
}

.headeProducts-title {
  margin-bottom: 40px;
}

span {
  font-size: 14px;
  text-transform: uppercase;
  color: #bdbdbd;
}
.heart-icon {
  background: none;
  border: 1px solid #f8f8f8;
  position: absolute;
  left: 1.5rem;
  top: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 32px;
  height: 32px;
  border-radius: 7px;
}

@media (min-width: 969px) and (max-width: 1009px) {
  .sneakers {
    display: flex;
    gap: 30px;
    flex-wrap: wrap;
    justify-content: flex-start;
    margin-left: 2rem;
  }
  .headeProducts-title {
    margin-bottom: 40px;
    margin-left: 30px;
  }
}
@media (min-width: 776px) and (max-width: 968.9px) {
  .sneakers {
    display: flex;
    gap: 30px;
    flex-wrap: wrap;
    justify-content: center;
    margin-left: 2rem;
  }
  .headeProducts-title {
    margin-bottom: 40px;
    text-align: center;
  }
}

@media (min-width: 480px) and (max-width: 775.9px) {
  .sneakers {
    display: flex;
    gap: 30px;
    flex-wrap: wrap;
    justify-content: center;
    margin-left: 2rem;
  }
  .headeProducts-title {
    margin-bottom: 40px;
    text-align: center;
  }
}

@media (max-width: 479.9px) {
  .sneakers {
    display: flex;
    gap: 30px;
    flex-wrap: wrap;
    justify-content: center;
    margin-left: 0rem;
  }
  .headeProducts-title {
    margin-bottom: 40px;
    text-align: center;
  }
}
</style>