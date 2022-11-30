<template>
  <div class="Navbar" v-bind:class="{ active: isActive === true }">
    <div class="nav-icons">
      <img class="nav-nike" src="@/assets/images/NIKE.svg" alt="" />
      <img
        class="nav-icon-logo"
        src="@/assets/images/simple-icons_nike.png"
        alt=""
      />
    </div>

    <div class="nav-serach">
      <ul class="nav-menu">
        <li><a href="#">Men</a></li>
        <li><a href="#">Women</a></li>
        <li><a href="#">Kids</a></li>
        <li><a href="#">Customise</a></li>
      </ul>

      <button class="nav-button">
        <img class="ros" src="@/assets/images/Vector.svg" alt="" />
        <span class="nav-search-text">search</span>
      </button>
      <img class="cart-icon" src="@/assets/images/Combined-Shape.svg" alt="" />

      <button class="close-icon" @click="isActive = !isActive">
        <i class="fa-solid fa-xmark fa-2x" v-if="!isActive"></i>
        <i class="fa-solid fa-bars fa-2x" v-if="isActive"></i>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  el: "#sidemenu",
  data() {
    return {
      isActive: false,
    };
  },
};
</script>

<style>
.Navbar {
  width: 1200px;
  max-width: 100%;

  margin: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px 99px 0px 140px;
}

.nav-icons {
  display: flex;
  gap: 14px;
}

.nav-icon-logo {
  width: 94px;
  height: 94px;
  object-fit: cover;
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 28px;
}
.nav-menu li {
  list-style: none;
}
.nav-menu li a {
  text-decoration: none;
  color: #ece2e2;
}

.nav-serach {
  display: flex;
  gap: 55px;
}
.nav-button {
  padding: 10px 60px 10px 10px;
  border-radius: 23px;
  border: none;
  display: flex;

  justify-content: space-between;
  align-items: center;
}
.nav-search-text {
  margin-left: 12px;
}
.close-icon {
  display: none;
}

/* media */

@media (min-width: 900px) and (max-width: 1200px) {
  .nav-menu {
    margin-right: 0rem;
  }
  .Navbar {
    padding: 0px 20px 0px 30px;
  }
}

@media (min-width: 300px) and (max-width: 899.9px) {
  .close-icon {
    background: none;
    border: none;
    display: inline-block;
    position: absolute;
    top: 1.6rem;
    right: 1rem;
  }
  .Navbar {
    width: 100%;
    max-width: 100%;
    z-index: 999;
    background: linear-gradient(
      129.86deg,
      #21e8c4 -20.42%,
      #459b17 -3.13%,
      #267b87 24.22%,
      #0f474f 72.75%
    );
    display: block;
    padding: 0px 99px 0px 140px;
    overflow: hidden;
    position: absolute;
    height: 100vh;
  }
  .active {
    height: 80px;
  }
  .isActive {
    height: 100vh;
  }

  .nav-serach {
    display: flex;
    justify-content: center;
  }
  .nav-menu {
    display: flex;
    flex-direction: column;

    gap: 48px;
    margin-top: 30px;
    justify-content: center;
  }
  .nav-icons {
    display: flex;
    justify-content: center;

    gap: 74px;
  }
  .nav-button {
    display: none;
  }
  .cart-icon {
    display: none;
  }
  .nav-nike {
    width: 50px;
  }
}
</style>