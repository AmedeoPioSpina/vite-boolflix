<template>
  <SearchBar @moviesListEmited="moveDataFunc" />
  <MoviesCardsContainer v-if="moviesList.length !== 0" :moviesListProp="moviesList" />
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
        moviesList: []
      }
    },
    methods: {
      moveDataFunc(list){
        this.moviesList = list;
      }
    },
  }
  </script>

<style scoped>

</style>
