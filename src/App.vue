<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
    
    </v-content>
  </v-app>
</template>

<script>


import Vue from 'vue';

import VueSuperagent from 'vue-superagent'


Vue.use(VueSuperagent) 

export default {
  name: 'App',
  mounted: function () {
    this.$http
      .get('https://shoppy.gg/api/v1/products/') 
      .set({ 'Authorization': 'miRtovzMxnHyGomQGTewS7WIxzaS3csQaTGKSh9vNRIJurFxSO', 'Access-Control-Allow-Origin': 'https://shoppy.gg', 'Access-Control-Allow-Methods':'GET, POST'})
      .set('Accept', 'application/json')
      .then(res => console.log(res))
      .catch(err => console.log(err));

  },
 
  data: () => ({
    //
  }),
};
</script>
