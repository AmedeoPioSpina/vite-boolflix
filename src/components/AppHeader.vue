<template lang="">
    <header>
        <section>
                <h1>
                    BOOLFLIX
                </h1>
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
<style lang="scss">
    
</style>