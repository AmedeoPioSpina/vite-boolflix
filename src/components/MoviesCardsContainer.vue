<template lang="">
    <ul>
        <MovieCards v-for="item in productsListProp" :key="item.id" :productInfoProp="item"/>
        
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
        "productsListProp"
    ],
}
</script>

<style lang="">
    
</style>