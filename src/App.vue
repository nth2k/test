<template>
  <div id="app">
    <h1>{{ test }}</h1>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      // loading: this.$store.state.loading,
      test: null,
    };
  },
  created() {
    fetch(
      "https://maps.googleapis.com/maps/api/geocode/json?language=ja&key=AIzaSyBJlb9fygUTGGIERrpCNovNaXZLgES1Wg8&address=2510047"
    )
      .then((response) => response.json())
      .then((data) => (this.test = data));
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
