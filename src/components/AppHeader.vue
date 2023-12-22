<template lang="">
    <header>
        <section>
            <div class="logo-container">
                <img src="" alt="">
            </div>
            <div class="search-bar-container">
                 <SearchBar />
            </div>
        </section>
    </header>
</template>
<script>
import SearchBar from './SearchBar.vue';
export default {
    name: "AppHeader",
    components: {
        SearchBar,
    }
}
</script>
<style lang="">
    
</style>