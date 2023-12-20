<template lang="">
    <li>
        <h2>
            {{ movieInfo.title }}
        </h2>
        <p>
            {{ movieInfo.original_title }}
        </p>
        <p>
            {{ movieInfo.original_language }}
        </p>
        <p>
            {{ movieInfo.vote_average }}
        </p>
    </li>
</template>
<script>
export default {
    name: "MovieCards",
    props: [
        "movieInfo"
    ],
    data() {
        return {
            
        }
    },
}
</script>
<style lang="">
    
</style>