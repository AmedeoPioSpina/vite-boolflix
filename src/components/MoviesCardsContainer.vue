<template lang="">
    <ul>
        <MovieCards v-for="item in productsList" :key="item.id" :productInfoProp="item"/>
        
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
            productsList: [...this.productsListProp[0],...this.productsListProp[1]]
        }
    },
    props: [
        "productsListProp"
    ],
}
</script>

<style lang="">
    
</style>