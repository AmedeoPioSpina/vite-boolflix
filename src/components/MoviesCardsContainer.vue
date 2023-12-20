<template lang="">
    <ul>
        <MovieCards v-for="item in moviesListProp" :key="item.id" :movieInfo="item"/>
        
    </ul>
</template>

<script>
import MovieCards from './MovieCards.vue';
export default {
    name: "MoviesCardsContainer",
    components:{
        MovieCards
    },
    data() {
        return {
            
        }
    },
    props: [
        "moviesListProp"
    ],
}
</script>

<style lang="">
    
</style>