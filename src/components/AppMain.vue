<script>
import axios from 'axios';
import PokemonList from './pokemons/PokemonList.vue';
import { store } from '../assets/data/store.js';
export default {
    components: { PokemonList },
    methods: {
        filterPokemon(type) {
            const uri = `${store.endpoint}?eq[type1]=${type}`;
            this.fetchPokemons(uri);
        },
        fetchTypes() {
            axios.get(store.endpoint + '/types1').then(res => {
                store.types = res.data;
            });
        },
        fetchPokemons(uri) {
            axios.get(uri).then(res => {
                store.pokemons = res.data.docs;
            });
        },
    },
    created() {
        this.fetchTypes();
    }

};
</script>
<template>
    <div class="background">
        <div class="container">
            <header>
                <h1 class="text-center py-5">Pokévuex</h1>
            </header>
            <main>
                <PokemonList @type-change="filterPokemon" />
            </main>
        </div>
    </div>
</template>
<style lang="scss" scoped>
@import 'bootstrap/scss/bootstrap.scss';

.background {
    background-image: url(src/assets/img/pokemon_bg.jpeg);
    background-repeat: no-repeat;
    background-size: cover;
    min-height: 100vh;
}

h1 {
    color: white;
}
</style>