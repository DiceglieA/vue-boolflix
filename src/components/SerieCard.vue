<template>
  <div>
    <ul>
      <li>{{ serie.title }}</li>
      <li>{{ serie.original_title }}</li>
      <li>{{ serie.original_language }}</li>
      <li>{{ serie.vote_average }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SerieCard',
  props: {
    serie: Object,
  },
};
</script>

<style lang="scss" scoped>

</style>
