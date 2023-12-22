<template lang="">
    <ul v-if="mixingProductsListFunc().length !== 0">
        <MovieCards v-for="product in mixingProductsListFunc()" :key="product.id" :productInfoProp="product"/>
    </ul>
    <p v-else>
        Cerca qualcosa...
    </p>
</template>

<script>
import MovieCards from './MovieCards.vue';
import { productsList } from '../js/productsList.js';
export default {
    name: "MoviesCardsContainer",
    components:{
        MovieCards
    },
    data() {
        return {
            productsList,
        }
    },
    methods: {
        mixingProductsListFunc(){
            return [...this.productsList.moviesList, ...this.productsList.tvSeriesList];
        }
    }
}
</script>

<style lang="">
    
</style>