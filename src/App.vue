<template>
  <div>
    <HeaderComp @search="searching" />
    <MainComp
      :movies="movies"
      :series="series"
    />
  </div>
</template>

<script>
import axios from 'axios';
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
  },
  data() {
    return {
      movieApi: 'https://api.themoviedb.org/3/search/movie',
      seriesApi: 'https://api.themoviedb.org/3/search/tv',
      apiKey: '61be2a28a2d6dd1d08a2030ee591fb8c',
      resultLanguage: 'it-IT',
      movies: [],
      series: [],
    };
  },
  methods: {
    searching(searchTitle) {
      this.title = searchTitle;
      axios.get(this.movieApi, {
        params: {
          api_key: this.apiKey,
          language: this.resultLanguage,
          query: this.title,
        },
      })
        .then((responseAxios) => {
          this.movies = responseAxios.data.results;
          console.log(this.movies);
        });

      axios.get(this.serieApi, {
        params: {
          api_key: this.apiKey,
          language: this.resultLanguage,
          query: this.title,
        },
      })
        .then((responseAxios) => {
          this.series = responseAxios.data.results;
          console.log(this.series);
        });
    },
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-decoration: none;
}
</style>
