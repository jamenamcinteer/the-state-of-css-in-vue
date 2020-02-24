<template>
  <div>
    <section class="section">
      <div class="container has-text-centered">
        <button
          class="button is-secondary is-medium"
          :class="{'is-loading': loading}"
          @click="fetchImages"
        >Get More Images</button>
      </div>
    </section>
    <section class="section is-paddingless">
      <div class="container">
        <div class="columns is-multiline">
          <div v-for="(dog, index) in dogs" :key="index" class="column is-one-third">
              <div class="box">
                <img :src="dog" class="dogImg" />
              </div>
          </div>
        </div>
      </div>
    </section>
  </div>
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

<style scoped>
.dogImg {
  object-fit: cover;
  height: 300px;
  width: 100%;
}
</style>