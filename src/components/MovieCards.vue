<template lang="">
    <li>
        <h2>
            {{
                checkKeyfunc("title","name")
            }}
        </h2>
        <p>
            {{ 
                checkKeyfunc("original_title","original_name")    
            }}
        </p>
        <img :src="lang_icons[`${productInfoProp.original_language}`]" :alt="productInfoProp.original_language">
        <p>
            {{ productInfoProp.vote_average }}
        </p>
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
        }
    },
}
</script>
<style lang="">
    
</style>