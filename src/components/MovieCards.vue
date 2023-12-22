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
        <p>
            {{ productInfoProp.original_language }}
        </p>
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