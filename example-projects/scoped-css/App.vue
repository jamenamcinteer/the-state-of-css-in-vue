<template>
  <div id="app">
    <Header />
    <Home />
  </div>
</template>

<script>
import Home from "./components/Home.vue";
import Header from "./components/Header"
export default {
  name: "App",
  components: {
    Home,
    Header
  }
};
</script>

<style>
body {
  background: #EEE;
  margin: 0;
  padding: 0;
}
</style>