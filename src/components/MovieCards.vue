<template lang="">
    <li>
        <div class="title-container">
            <span>
                Titolo:
            </span>
            <h2>
                {{
                    checkKeyfunc("title","name")
                }}
            </h2>
        </div>
        <div class="original-title-container">
            <span>
                Titolo originale:
            </span>
            <p>
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
            <span>
                Overview:
            </span>
            <p>
                {{
                    productInfoProp.overview
                }}
            </p>
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
                    console.log(this.productInfoProp[`${keyA}`])
                    return this.productInfoProp[`${keyA}`]
                }
                else{ 
                    console.log(this.productInfoProp[`${keyB}`])
                    return this.productInfoProp[`${keyB}`]
                }
        },
        voteScaleChangeFunc(vote){
            return Math.round( (5 * vote) / 10 );
        }
    },
}
</script>
<style lang="">
    
</style>