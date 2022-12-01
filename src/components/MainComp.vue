<template>
  <div class="container">
    <MovieCard
      v-for="movie in movies"
      :key="movie.id"
      :movie="movie"
    />
  </div>
</template>

<script>
import MovieCard from '@/components/MovieCard.vue';

export default {
  name: 'MainComp',
  components: {
    MovieCard,
  },
  props: {
    movies: Array,
    series: Array,
  },
};
</script>

<style lang="scss" scoped>
.container {
  height: 90vh;
  background-color: rgb(32, 32, 32);
}
</style>
