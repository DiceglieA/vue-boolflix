<template>
  <div>
    <HeaderComp @search="searching" />
    <MainComp :movies="movies" />
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
      apiKey: '61be2a28a2d6dd1d08a2030ee591fb8c',
      resultLanguage: 'it-IT',
      movies: [],
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
