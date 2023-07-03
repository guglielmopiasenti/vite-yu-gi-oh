<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import AppMain from './components/AppMain.vue';
import { store } from 'src/assets/data/store.js';
export default {
    components: { AppMain },

    created() {
        axios.get(endpoint).then(res => {
            store.pokemons = res.data.docs;
        });
    },
};
</script>
<template>
    <AppMain />
</template>

<style lang="scss">
@use 'src/assets/scss/style.scss';
</style>