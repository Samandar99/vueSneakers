<template>
  <section class="banner-wrapper">
    <div class="banner-tite">
      <h1>JUST DO IT</h1>
      <div class="banner-nike2">
        <img class="banner-nike" src="@/assets/images/nike.png" alt="" />
      </div>

      <div class="ban">
        <p>Nike Court Zoom Vapor Cage 4 Rafa</p>
      </div>
    </div>

    <div class="banner-info">
      <div>
        <p class="banner-info-text">
          Innovated to withstand your toughest matches, this updated design puts
          flexible, durable materials exactly where they're needed most.
        </p>
        <div class="shop-button">
          <button class="banner-info-button">SHOP NOW</button>
        </div>
      </div>
      <div class="banner-right">
        <div class="banner-sneak" v-for="sneaker in sneakers" :key="sneaker.id">
          <img :src="sneaker.imgs" alt="" />
          <p>{{ sneaker.name }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      sneakers: [
        {
          id: 1,
          name: "rafa-hard-court",
          imgs: require("../assets/images/sneaker.png"),
        },
        {
          id: 2,
          name: "pro-hard-court",
          imgs: require("../assets/images/sneaker1.png"),
        },
        {
          id: 3,
          name: "Vapor Cage 4 Rafa",
          imgs: require("../assets/images/sneaker.png"),
        },
      ],
    };
  },
};
</script>

<style scoped>
.banner-wrapper {
  max-width: 1000px;
  width: 100%;

  margin: auto;
}
.shop-button {
  display: inline-block;
}
.banner-info {
  display: flex;
  gap: 3rem;
}

.banner-wrapper h1 {
  font-size: 64px;
  font-weight: 900;
  width: 145px;
  line-height: 129%;
  color: #454040;
}
.banner-tite {
  display: flex;
  align-items: center;
  gap: 300px;
  position: relative;
}

.banner-nike {
  width: 584px;
  height: 381px;
  object-fit: cover;
  transform: rotate(-7deg);
}
.banner-nike2 {
  width: 584px;
  height: 381px;
  z-index: 99;
  overflow: hidden;
}

.ban {
  width: 373px;
  height: 84px;
  background: #d9d9d9;
  box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.25);
  border-radius: 71px;
  position: absolute;
  padding: 10px 23px;
  right: 10rem;
}
.ban p {
  color: #185955;
  width: 190px;
  font-weight: 900;
  font-size: 18px;
  letter-spacing: 0.015em;
}

.banner-info-text {
  width: 420px;
  text-transform: capitalize;
  color: #454040;
  font-size: 18px;
  letter-spacing: 0.015em;
}
.banner-info-button {
  padding: 16px 50px;
  background: linear-gradient(
    106.81deg,
    #179b93 43.2%,
    rgba(217, 217, 217, 0.71) 61.6%
  );
  border-radius: 38px;
  margin-top: 45px;
  border: none;
  color: rgba(250, 255, 35, 0.99);
  font-weight: 700;
  text-transform: uppercase;
  font-size: 20px;
  cursor: pointer;
  transition: all 0.3s ease;
}
.banner-info-button:hover {
  background: none;
  border: 1px solid #cfcdcd;
  color: #179b93;
}

.banner-right {
  margin-top: 10rem;
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}
.banner-sneak {
  width: 152px;
  height: 139px;
  background: linear-gradient(
    180deg,
    rgba(250, 255, 35, 0.99) -4.65%,
    rgba(250, 255, 35, 0) 100%
  );
  border-radius: 28px;
  margin-bottom: 5rem;
  text-align: center;
  transition: all 0.2s ease;
}

.banner-sneak:hover {
  transform: scale(1.1);
  background: #faff23;
}

.banner-sneak img {
  display: block;
}
.banner-sneak p {
  color: #ffffff;

  display: block;
}

/* media */

@media (min-width: 969px) and (max-width: 1009px) {
  .banner-tite {
    display: flex;
    justify-content: space-around;
    gap: 100px;
    position: relative;
  }
}

@media (min-width: 766px) and (max-width: 968px) {
  .banner-tite {
    display: flex;
    flex-direction: column;
    gap: 0px;
    position: relative;
  }

  .ban {
    width: 373px;
    height: 84px;
    box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.25);
    border-radius: 71px;
    position: absolute;
    padding: 10px 23px;
    right: 20rem;
    top: 27rem;
  }
  .banner-info {
    display: flex;
    justify-content: center;
    flex-direction: column;
    text-align: center;
  }
  .banner-info-text {
    margin: auto;
  }
  h1 {
    margin-top: 5rem;
  }
  .banner-right {
    margin-top: 0rem;
    display: flex;
    gap: 16px;
    justify-content: center;
  }
}

@media (min-width: 550px) and (max-width: 765.9px) {
  .banner-tite {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0px;
    position: relative;
  }
  h1 {
    margin-top: 5rem;
  }

  .ban {
    width: 373px;
    height: 84px;
    box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.25);
    border-radius: 71px;
    position: absolute;
    padding: 10px 23px;

    margin: 380px auto;
  }
  .banner-info {
    display: flex;
    justify-content: center;
    flex-direction: column;
    text-align: center;
  }
  .banner-info-text {
    margin: 20px auto;
  }
  .banner-nike {
    width: 384px;
    height: 181px;
    object-fit: cover;
    transform: rotate(-7deg);
    margin-top: 2rem;
  }
  .banner-nike2 {
    width: 384px;
    height: 181px;
    z-index: 99;
    overflow: hidden;
  }
  .banner-right {
    margin-top: 0rem;
    display: flex;
    gap: 16px;
    justify-content: center;
    flex-wrap: wrap;
  }
}

@media (max-width: 549.9px) {
  .banner-tite {
    display: flex;
    flex-direction: column;
    gap: 0px;
    position: relative;
    justify-content: s;
  }
  h1 {
    margin-top: 5rem;
  }

  .ban {
    width: 273px;
    height: 84px;
    box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.25);
    border-radius: 71px;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    padding: 10px 23px;
    margin: 400px auto;
  }

  .banner-info {
    display: flex;
    justify-content: center;
    flex-direction: column;
    text-align: center;
  }
  .banner-info-text {
    margin: 20px auto;
  }
  .banner-nike {
    width: 284px;
    height: 181px;
    object-fit: cover;
    transform: rotate(-7deg);
    margin-top: 2rem;
  }
  .banner-nike2 {
    width: 284px;
    height: 181px;
    z-index: 99;
    overflow: hidden;
  }
  .banner-info-text {
    width: 300px;
    text-transform: capitalize;
    color: #ffffff;
    font-size: 18px;
    letter-spacing: 0.015em;
  }
  .banner-right {
    margin-top: 0rem;
    display: flex;
    gap: 16px;
    justify-content: center;
    flex-direction: column;
    margin: auto;
  }
}
</style>