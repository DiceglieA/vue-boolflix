<template>
  <div class="container">
    <MovieCard
      v-for="movie in movies"
      :key="movie.id"
      :movie="movie"
    />
    <SerieCard
      v-for="serie in series"
      :key="serie.id"
      :serie="serie"
    />
  </div>
</template>

<script>
import MovieCard from '@/components/MovieCard.vue';
import SerieCard from '@/components/SerieCard.vue';

export default {
  name: 'MainComp',
  components: {
    MovieCard,
    SerieCard,
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
