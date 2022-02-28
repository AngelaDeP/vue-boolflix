<template>
  <div id="app">
    <MyHeader @search=generateFilms />
    <MyMain :filmCatalogue="filmCatalogue" />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'

const axios = require('axios');

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  data() {
    return {
      filmCatalogue: []
    }
  },
  methods: {
    generateFilms(keyword) {

      axios.get('https://api.themoviedb.org/3/search/movie?api_key=142d3e745767ac3cb528a724ffa3c28d&query=' + keyword)
      .then((response) => {
        console.log(response);
        this.filmCatalogue = response.data.results;
      })
      .catch(function (error) {
        console.log(error);
      })
      .then (function () {
        // always executed
      });
    }
  }
}
</script>

<style lang="scss">
@import "./assets/style/general-style.scss";
</style>
