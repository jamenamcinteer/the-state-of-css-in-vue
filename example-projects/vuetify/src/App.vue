<template>
  <v-app>
    <v-app-bar
      app
      color="#34495e"
      dark
    >
      <div class="d-flex align-center">
        <v-toolbar-title>Random Corgi Images</v-toolbar-title>
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">View on Github</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
      <CorgiGrid/>
    </v-content>
  </v-app>
</template>

<script>
import CorgiGrid from './components/CorgiGrid';

export default {
  name: 'App',

  components: {
    CorgiGrid,
  },

  data: () => ({
    //
  }),
};
</script>
