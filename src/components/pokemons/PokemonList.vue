<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
export default {
    data() {
        return {
            pokemon: []

        }
    },
    created() {
        axios.get(endpoint).then(res => {
            this.pokemon = res.data.docs;
        });
    }
};
</script>
<template>
    <section id="pokemon"></section>
</template>
<style></style>