<template lang="">
    <li>
        <div class="cover-image-container">
            <img :src="`https://image.tmdb.org/t/p/w500${productInfoProp.poster_path} `" alt="Cover image">
        </div>

        <div class="product-info-container">
            <div class="title-container">
                <span>
                    Titolo:
                </span>
                <p>
                    {{
                        checkKeyfunc("title","name")
                    }}
                </p>
            </div>
            <div class="original-title-container">
                <p>
                    <span>
                        Titolo originale:
                    </span>
                    {{ 
                        checkKeyfunc("original_title","original_name")    
                    }}
                </p>
            </div>
            <div class="language-container">
                <span>
                    Lingua:
                </span>
                <img :src="lang_icons[`${productInfoProp.original_language}`]" :alt="productInfoProp.original_language">
            </div>
            <div class="vote-container">
                <span>
                    Voto:
                </span>
                <img v-for="item in voteScaleChangeFunc(productInfoProp.vote_average)" src="https://img.icons8.com/office/40/star--v1.png" alt="">
            </div>
            <div class="overview-contianer">
                <p>
                    <span>
                        Overview:
                    </span>
                    {{
                        productInfoProp.overview
                    }}
                </p>
            </div>
        </div>
    </li>
</template>
<script>
export default {
    name: "MovieCards",
    props: [
        "productInfoProp"
    ],
    data() {
        return {
            lang_icons: {
                "cn" : "https://img.icons8.com/office/40/china.png",
                "de" : "https://img.icons8.com/office/40/germany.png",
                "en" : "https://img.icons8.com/office/40/great-britain.png",
                "fr" : "https://img.icons8.com/office/40/france.png",
                "it" : "https://img.icons8.com/office/16/italy.png",
                "ja" : "https://img.icons8.com/office/40/japan.png",
                "ko" : "https://img.icons8.com/office/40/south-korea.png",
                "sp" : "https://img.icons8.com/office/40/spain-2.png",
            },
        }
    },
    methods: {
        checkKeyfunc(keyA, keyB){
            if(this.productInfoProp[`${keyA}`] !== undefined){
                    return this.productInfoProp[`${keyA}`]
                }
                else{ 
                    return this.productInfoProp[`${keyB}`]
                }
        },
        voteScaleChangeFunc(vote){
            return Math.round( (5 * vote) / 10 );
        }
    },
}
</script>
<style lang="scss">
    
</style>