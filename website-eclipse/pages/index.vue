<template light>
  <div>
    <body class="body">
      <!-- LOGO ECLIPSE -->
      <section class="hero">
        <img
          src="~assets/images/logo-eclipse-white-tnp.png"
          class="hero__img"
        />
        <h1 class="white--text text-xs-center text-h1 hero__text">
          Ilmu Komputer 54
        </h1>
      </section>

      <!-- ISI -->
      <v-container mt-10 mb-15 col-12>
        <v-layout row align-center justify-center fill-height wrap>
          <v-flex xs12 lg5>
            <p class="text-h1 text-center font-weight-medium mb-10 welcome">
              Selamat Datang di Wesbite Eclipse
            </p>
          </v-flex>
        </v-layout>
        <!-- COUNTER JUMLAH MAHASISWA -->
        <v-layout row align-center justify-center fill-height wrap mt-5>
          <v-flex xs12 lg5>
            <div class="text-h1 text-center font-weight-medium mb-5">
              <number
                class="bold transition"
                ref="number1"
                :class="{ scaleBig: scaleClass }"
                :from="numberFrom"
                :to="numberTo"
                :duration="duration"
                easing="Power1.easeOut"
              />
            </div>
            <p class="text-h3 text-center">Mahasiswa</p>
          </v-flex>
        </v-layout>
      </v-container>
    </body>
  </div>
</template>

<script>
import EclipseLogo from "~/assets/images/logo-eclipse-white-tnp.png";

export default {
  components: {
    EclipseLogo,
  },
  data() {
    return {
      numberFrom: 0,
      numberTo: 96,
      duration: 2,
      scaleClass: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.hero {
  background-color: #1c1c1c;
  background-size: cover;
  background-position: 30% 0;
  display: flex;
  flex-direction: column;
  margin-top: 60px;
  border: 175px;
  height: calc(100vh - 50px);
  justify-content: center;
  align-items: center;
  &__text {
    max-height: 300px;
    display: flex;
    height: inherit;
    align-items: center;
    //font-family: "Nunito" !important;
  }
  &__img {
    display: flex;
    height: 50vh;
    align-items: center;
  }
  .welcome {
    width: 50vw;
  }
}
</style>