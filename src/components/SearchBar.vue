<template lang="">
    <div>
        <input type="text" v-model="inputValue"  @keyup.enter="axiosFunc(inputValue), inputValue=''">
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
            moviesList: [],
            tvList: []
        }
    },
    methods: {
        axiosFunc(query) {            
            axios.get(`https://api.themoviedb.org/3/search/movie?api_key=a2cb9b8358fbf60f421cced84a3dd562&language=it-IT&query=${query}`)
            .then(resp => {
                this.moviesList= resp.data.results
                axios.get(`https://api.themoviedb.org/3/search/tv?api_key=a2cb9b8358fbf60f421cced84a3dd562&language=it-IT&query=${query}`)
                .then(resp => {
                    this.tvList= resp.data.results
                    this.$emit("productsListEmited", this.moviesList, this.tvList)
                })
                .catch(err => console.warn(err));
            })
            .catch(err => console.warn(err));
            
            
        }
    },
}
</script>

<style lang="">
    
</style>