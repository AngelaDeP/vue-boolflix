<template>
  <div id="app">
    <MyHeader @search=combinedSearch />
    <MyMain :filmCatalogue="filmCatalogue" :tvSeriesCatalogue="tvSeriesCatalogue" />
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
      filmCatalogue: [],
      tvSeriesCatalogue: []
    }
  },
  methods: {
    generateFilms(keyword) {

      axios.get('https://api.themoviedb.org/3/search/movie?api_key=142d3e745767ac3cb528a724ffa3c28d&query=' + keyword + '&language=it-IT')
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
    },
    generateTvSeries(keyword) {

      axios.get('https://api.themoviedb.org/3/search/tv?api_key=142d3e745767ac3cb528a724ffa3c28d&query=' + keyword + '&language=it-IT')
      .then((response) => {
        console.log(response);
        this.tvSeriesCatalogue = response.data.results;
      })
      .catch(function (error) {
        console.log(error);
      })
      .then (function () {
        // always executed
      });
    },
    combinedSearch(keyword){
      this.generateFilms(keyword);
      this.generateTvSeries(keyword);
    }
  }
}
</script>

<style lang="scss">
@import "./assets/style/general-style.scss";
</style>
