<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import AppMain from './components/AppMain.vue';
import { store } from './assets/data/store.js';
import SearchForm from './components/pokemons/SearchForm.vue';
export default {
    components: { AppMain, SearchForm },
    props: {
        endpoint: {
            type: String,
            required: true
        }
    },
    methods: {
        filterPokemon(type) {
            const uri = `${endpoint} + /types1=${type} `;
            this.fetchPokemons(uri);
        },
        fetchTypes() {
            axios.get(endpoint + '/types1').then(res => {
                store.types = res.data;
            })
        }
    },

    created() {
        // Fetching data from the specified endpoint using axios
        axios.get(store.endpoint).then(res => {
            // Assigning the received data to the 'pokemons' property in the store
            store.pokemons = res.data.docs;
        });
        this.fetchTypes();
    },
};
</script>
<template>
    <!-- Rendering the AppMain component -->
    <AppMain :endpoint="endpoint" />
</template>

<style lang="scss">
@use 'src/assets/scss/style.scss';
</style>