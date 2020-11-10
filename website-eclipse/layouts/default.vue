<template>
  <div>
    <v-app>
      <!-- NAVBAR -->
      <v-navigation-drawer
        v-model="drawer"
        widt="200"
        height="100vh"
        :clipped="clipped"
        fixed
        temporary
        app
        light
      >
        <v-list two-line>
          <v-list-item
            active-class="tabred"
            :ripple="{ class: 'orange--text' }"
            v-for="(item, i) in items"
            :to="item.to"
            :key="i"
            router
            nuxt
            exact
          >
            <v-list-item-content>
              <v-list-item-title v-text="item.title" class="title" />
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>

      <!-- TOOLBAR -->
      <v-app-bar
        dark
        app
        scroll-off-screen
        color="black"
        clipped-left
        fixed
        height="72"
      >
        <v-icon @click.stop="drawer = !drawer" class="hidden-md-and-up"
          >mdi-view-headline</v-icon
        >
        <nuxt-link to="/">
          <img
            src="~assets/images/logo-eclipse-white-tnp.png"
            alt="eclipse"
            class="nav__logo hidden-sm-and-down"
          />
        </nuxt-link>
        <v-spacer></v-spacer>
        <img
          src="~assets/images/logo-eclipse-white-tnp.png"
          alt="eclipse"
          class="nav__logo--small hidden-md-and-up"
        />
        <v-toolbar-items
          class="hidden-sm-and-down"
          v-for="(item, i) in items"
          :key="i"
        >
          <v-btn
            exact-active-class="tabred"
            active-class="tabred"
            text
            :to="item.to"
            exact
            nuxt
            :ripple="{ class: 'orange--text' }"
          >
            {{ item.title }}
          </v-btn>
        </v-toolbar-items>
      </v-app-bar>

      <Nuxt />

      <!-- FOOTER -->
      <v-footer :absolute="!fixed" app dark>
        <v-layout justify-center row wrap>
          <span>Copyright &copy; 2021 Eclipse</span>
        </v-layout>
      </v-footer>
    </v-app>
  </div>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-home",
          title: "Beranda",
          to: "/",
        },
        {
          icon: "mdi-account-group",
          title: "Profil KOM 54",
          to: "/profil",
        },
        {
          icon: "mdi-chart-bubble",
          title: "Cerita Kuliah",
          to: "/cerita",
        },
        {
          icon: "mdi-book",
          title: "Amunisi Kuliah",
          to: "/amunisi",
        },
        {
          icon: "mdi-school",
          title: "Kolokium",
          to: "/nanti",
        },
        {
          icon: "mdi-login",
          title: "Login",
          to: "/login",
        },
      ],
      title: "Vuetify.js",
    };
  },
};
</script>

<style lang="scss">
.nav__logo {
  margin-top: 6px;
  height: 62px;
}

.nav__logo--small {
  height: 62px;
}

.tabred {
  color: red !important;
}
</style>