<template lang="">
        <input type="text" placeholder="Cerca" v-model="inputValue"  @keyup.enter="axiosFunc(inputValue), inputValue=''">
</template>

<script>
import axios from 'axios';
import { productsList } from '../js/productsList.js';

export default {
    name: "SearchBar",
    data() {
        return {
            productsList,
            inputValue: "",
            moviesList: [],
            tvSeriesList: []
        }
    },
    methods: {
        axiosFunc(query) {            
            axios.get(`https://api.themoviedb.org/3/search/movie?api_key=a2cb9b8358fbf60f421cced84a3dd562&language=it-IT&query=${query}`)
            .then(resp => {
                this.moviesList= resp.data.results
                axios.get(`https://api.themoviedb.org/3/search/tv?api_key=a2cb9b8358fbf60f421cced84a3dd562&language=it-IT&query=${query}`)
                .then(resp => {
                    this.tvSeriesList= resp.data.results;
                    productsList.moviesList = this.moviesList;
                    productsList.tvSeriesList = this.tvSeriesList;
                })
                .catch(err => console.warn(err));
            })
            .catch(err => console.warn(err));
            
            
        }
    },
}
</script>

<style lang="scss">
    
</style>