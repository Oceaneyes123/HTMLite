<template>
  <v-container>
    <div class="d-flex justify-center">
      <v-btn color="success title hidden-sm-and-down" @click="output = code" large>
        <v-icon class="mr-3">fas fa-running</v-icon>Run
      </v-btn>
    </div>
    <v-row class="text-center h-100">
      <v-col cols="12" md="6">
        <v-textarea v-model="code" filled outlined height="100vh"></v-textarea>
      </v-col>
      <v-col cols="12" class="d-md-none d-block mb-5">
        <v-btn color="success title" @click="output = code" large>
          <v-icon class="mr-3">fas fa-running</v-icon>Run
        </v-btn>
      </v-col>
      <v-col cols="12" md="6">
        <v-card min-height="95%" class="text-left pa-2 rounded-lg" light>
          <div v-html="output"></div>
        </v-card>
      </v-col>
    </v-row>
    <div class="d-flex justify-end">
      <v-hover v-slot:default="{ hover }">
        <div
          class="caption"
          :class="hover ? 'blue--text darken-2': 'text--secondary'"
          style="cursor:pointer"
          @click="about = true"
        >About Me</div>
      </v-hover>
      <v-dialog v-model="about" max-width="500">
        <v-card>
          <v-card-title>About Me</v-card-title>
          <v-card-text>Jezrel Dave Sondia - Web Developer</v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="primary" @click="about = false">Close</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
  </v-container>
</template>

<style  scoped>
.container .row {
  min-height: 100vh;
}
</style>

<script>
export default {
  name: "Main",
  data: () => ({
    about: false,
    code: `<!DOCTYPE html>
      <html>

              <head>
              </head>

              <body>

                   <!-- Don't mind me. I'm a comment -->

                  <h1>Hello</h1>
                  <h6>Your Code Here</h6>

              </body>

      </html>`,
    output: "",
  }),

  mounted() {
    this.output = this.code;
  },
  methods: {},
};
</script>
