<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import AppMain from './components/AppMain.vue';
import { store } from './assets/data/store.js';
import SearchForm from './components/pokemons/SearchForm.vue';
export default {
    components: { AppMain, SearchForm },

    created() {
        // Fetching data from the specified endpoint using axios
        axios.get(endpoint).then(res => {
            // Assigning the received data to the 'pokemons' property in the store
            store.pokemons = res.data.docs;
        });
    },
};
</script>
<template>
    <!-- Rendering the AppMain component -->
    <AppMain />
</template>

<style lang="scss">
@use 'src/assets/scss/style.scss';
</style>