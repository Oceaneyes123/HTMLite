<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex font-weight-bold align-center">
        <span class="display-2 font-weight-bold mr-5">{{logo}}</span>
        <span class="display hidden-sm-and-down">HTMLite</span>
      </div>

      <v-spacer></v-spacer>
      <div class="d-flex font-weight-bold align-center">
        <v-switch v-model="darkSwitch" class="mt-5"></v-switch>
        <span class="mr-md-5">Dark Mode</span>
        <v-btn
          depressed
          href="https://ko-fi.com/jezreldavesondia"
          color="#ff5f5f"
          class="rounded-pill ml-7"
          target="_blank"
          :fab="screen < 960"
        >
          <v-img src="https://storage.ko-fi.com/cdn/cuplogo-sm.png" width="30" class="mr-md-2" />
          <span class="hidden-sm-and-down">Buy me a Coffee</span>
        </v-btn>
      </div>
    </v-app-bar>

    <v-main>
      <v-card :dark="darkSwitch">
        <Main></Main>
      </v-card>
    </v-main>
  </v-app>
</template>

<style>
#app {
  font-family: "Baloo Tamma 2", cursive;
}
</style>

<script>
import Main from "./components/Main";

export default {
  name: "App",

  components: {
    Main,
  },

  mounted() {
    console.log(this.screen);
  },

  data: () => ({
    logo: "</>",
    darkSwitch: false,
    screen: screen.width,
  }),

  created() {
    window.addEventListener("resize", this.onResize());
  },

  methods: {
    onResize() {
      this.screen = screen.width;
      console.log(this.screen);
    },
  },
};
</script>
