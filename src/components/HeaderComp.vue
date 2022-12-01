<template>
  <header>
    <div class="title">
      <a href="!#">BOOLFLIX</a>
    </div>
    <div class="selection">
      <form @submit.prevent="$emit('search', searchTitle)">
        <label for="search">
          <input
            id="search"
            v-model="searchTitle"
            type="text"
            name="search"
            placeholder="digita qui"
          >
          <button>Invia</button>
        </label>
      </form>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComp',
  data() {
    return {
      searchTitle: '',
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  height: 10vh;
  background-color: black;
  display: flex;
  justify-content: space-between ;
  align-items: center;
  padding: 0 2rem;
}
.title {
  a {
    color: red;
    font-size: 30px;
    font-weight: bolder;
  }
}
#search {
  border-radius: 20px;
  padding: 2px 5px;
  cursor: pointer
}
button {
  margin: 0 .5rem;
  color: red;
  background-color: black;
  border: 1px solid white;
  border-radius: 20px;
  padding: 2px 5px;
  cursor: pointer;
}
</style>
