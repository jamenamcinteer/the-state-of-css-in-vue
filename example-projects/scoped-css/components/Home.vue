<template>
  <div>
    <div class="buttonContainer">
      <button class="button" @click="fetchImages">Get More Images</button>
    </div>
    <div class="dogGrid">
      <div v-for="(dog, index) in dogs" :key="index" class="dogCard">
        <img :src="dog" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {
  },
  data: function() {
    return {
      dogs: []
    };
  },
  mounted() {
    this.fetchImages();
  },
  methods: {
    fetchImages() {
      fetch('https://dog.ceo/api/breed/corgi/images/random/6')
        .then((response) => {
          return response.json();
        })
        .then((myJson) => {
          this.dogs = myJson.message;
          console.log(myJson);
        });
    }
  }
};
</script>

<style scoped>
.buttonContainer {
  padding: 40px;
  text-align: center;
  margin: 0;
}
.button {
  background: rgb(221, 70, 0);
  color: white;
  border: 4px solid transparent;
  font-size: 18px;
  padding: 10px;
  border-radius: 4px;
}
.button:hover {
  cursor: pointer;
  box-shadow: 0 4px 8px rgba(0, 0, 0, .1);
}
.button:focus {
  border: 4px solid #CCC;
}
.dogGrid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 20px;
  margin: 0 40px;
}
.dogCard {
  background: #FFFFFF;
  box-shadow: 0 4px 8px rgba(0, 0, 0, .1);
  padding: 20px;
}
img {
  object-fit: cover;
  height: 300px;
  width: 100%;
}
</style>