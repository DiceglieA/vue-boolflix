<template>
  <div class="container">
    <div>
      <div class="card">
        <div>{{ movie.title }}</div>
        <div>{{ movie.original_title }}</div>
        <lang-flag :iso="movie.original_language" />
        <div>{{ movie.vote_average }}</div>
      </div>
    </div>
  </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';

export default {
  name: 'MovieCard',
  components: {
    LangFlag,
  },
  props: {
    movie: Object,
  },
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-wrap: wrap;
}
.card {
  background-color: salmon;
  height: 300px;
  width: 240px;
}
</style>
