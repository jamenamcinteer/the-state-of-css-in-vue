<template>
  <v-container class="grey lighten-5" fluid>
    <div class="text-center ma-8">
        <v-btn :loading="loading" :disabled="loading" @click="fetchImages" color="rgb(221, 70, 0)" class="white--text" x-large>Get More Images</v-btn>
    </div>
    <v-row>
      <v-col
        v-for="(dog, index) in dogs"
        :key="index"
        cols="12"
        sm="4"
      >
        <v-card
          class="pa-2"
          outlined
          tile
        >
          <v-img :src="dog" height="300" class="grey lighten-2">
            <template v-slot:placeholder>
              <v-row
                class="fill-height ma-0"
                align="center"
                justify="center"
              >
                <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
              </v-row>
            </template>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'CorgiGrid',

    data: () => ({
      dogs: [],
      loading: false
    }),
    mounted() {
    this.fetchImages();
  },
  methods: {
    fetchImages() {
      this.loading = true;
      fetch('https://dog.ceo/api/breed/corgi/images/random/6')
        .then((response) => {
          return response.json();
        })
        .then((myJson) => {
          this.dogs = myJson.message;
          this.loading = false;
        });
    }
  }
  }
</script>
