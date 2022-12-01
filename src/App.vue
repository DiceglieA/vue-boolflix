<template>
  <div>
    <HeaderComp @search="searching" />
    <MainComp />
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
      baseApi: 'https://api.themoviedb.org/3',
      apiKey: '61be2a28a2d6dd1d08a2030ee591fb8c',
      searchTitle: '',
    };
  },
  methods: {
    searching(searchTitle) {
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.apiKey}&query=${searchTitle}`)
        .then((response) => {
          console.log(response.data.result);
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
