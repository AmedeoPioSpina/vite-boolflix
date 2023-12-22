<template>
  <SearchBar @productsListEmited="moveDataFunc" />
  <MoviesCardsContainer v-if="productsList.length !== 0" :productsListProp="productsList" />
  <div v-else>
    <p>Cerca qualcosa...</p>
  </div>
</template>

  <script>
  import SearchBar from './components/SearchBar.vue';
  import MoviesCardsContainer from './components/MoviesCardsContainer.vue';
  export default {
    components: {
      SearchBar,
      MoviesCardsContainer
    },
    data() {
      return {
        productsList: []
      }
    },
    methods: {
      moveDataFunc(list){
        this.productsList = list;
      }
    },
  }
  </script>

<style scoped>

</style>
