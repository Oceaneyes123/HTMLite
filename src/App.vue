<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex display-1 font-weight-bold align-center">HTMLite</div>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <Main></Main>
    </v-main>
  </v-app>
</template>

<script>
import Main from "./components/Main";

export default {
  name: "App",

  components: {
    Main,
  },

  data: () => ({
    //
  }),
};
</script>
