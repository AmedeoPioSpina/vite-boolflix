<template lang="">
    <div>
        <input type="text" v-model="inputValue"  @keyup.enter="axiosFunc(urlTMDB + inputValue), inputValue=''">
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: "SearchBar",
    data() {
        return {
            inputValue: "",
            urlTMDB: "https://api.themoviedb.org/3/search/movie?api_key=a2cb9b8358fbf60f421cced84a3dd562&language=it-IT&query=",
            moviesList: []
        }
    },
    methods: {
        axiosFunc(url) {            
            return axios.get(url)
            .then(resp => {
                this.moviesList= resp.data.results
                return this.$emit("moviesListEmited", this.moviesList)
            })
            .catch(err => console.warn(err));
        }
    },
}
</script>

<style lang="">
    
</style>