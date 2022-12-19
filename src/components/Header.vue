<template>
  <section class="container__banner">
    <div class="navbar">
      <nav :class="{ active: !openMenu }">
        <div class="logo__nav">
          <img src="@/assets/images/NIKE.svg" alt="" />
          <img
            class="nike__icon"
            src="@/assets/images/simple-icons_nike.png"
            alt=""
          />
        </div>

        <div class="nav__left" :class="{ actives: !openMenu }">
          <ul class="nav-items">
            <li><a href="">Home</a></li>
            <li><a href="">Women</a></li>
            <li><a href="">Kids</a></li>
            <li><a href="">Customise</a></li>
          </ul>
          
          <div class="nav__Search">
            <div class="nav__input-search">
              <img class="cart__icon" src="@/assets/images/Vector.svg" alt="" />
              <input type="text" placeholder="Search" />
            </div>
            <div class="cart-icons">
              <img src="@/assets/images/Combined-Shape.svg" alt="" />
            </div>
          </div>
        </div>
        <button class="btn-close" @click="openMenu = !openMenu">
          <i class="fa fa-times fa-2x close-icon" v-if="openMenu"></i>
          <i class="fa-solid fa-bars fa-2x close-icon" v-else></i>
        </button>
      </nav>
    </div>

    <div class="banner">
      <div class="banner__left">
        <h1>JUST DO IT</h1>
        <p class="banner__text">
          Innovated to withstand your toughest matches, this updated design puts
          flexible, durable materials exactly where they're needed most.
        </p>
        <button class="banner__btn">SHOP NOW</button>
      </div>
      <div class="banner__right">
        <img class="banner__foto" src="@/assets/images/nike.png" alt="" />
        <div class="os">
          <p>NikeCourt Zoom Vapor Cage 4 Rafa</p>
        </div>

        <div class="banner__cards">
          <div class="banner__card">
            <img src="@/assets/images/sneaker.png" alt="" />
          </div>
          <div class="banner__card">
            <img src="@/assets/images/sneaker1.png" alt="" />
          </div>
          <div class="banner__card">
            <img src="@/assets/images/sneaker.png" alt="" />
          </div>
        </div>
      </div>
    </div>
  </section>
  <router-view/>
</template>

<script>
export default {
  data() {
    return {
      openMenu: true,
    };
  },
};
</script>

<style>
</style>