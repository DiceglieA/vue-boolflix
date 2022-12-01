<template>
  <div>
    <div>
      <div>{{ serie.title }}</div>
      <div>{{ serie.original_title }}</div>
      <lang-flag :iso="movie.original_language" />
      <div>{{ serie.vote_average }}</div>
    </div>
  </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';

export default {
  name: 'SerieCard',
  components: {
    LangFlag,
  },
  props: {
    serie: Object,
  },
};
</script>

<style lang="scss" scoped>

</style>
