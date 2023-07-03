<script>
import PokemonCard from './PokemonCard.vue';
import { store } from '../../assets/data/store.js';
export default {
    components: { PokemonCard },
    data() {
        return { store: store }
    }
};
</script>
<template>
    <section id="pokemons">
        <div class="row g-4 row-cols-2 row-cols-md-3 row-cols-lg-4">
            <div class="col" v-for="pokemon in store.pokemons" :key="pokemon.number">
                <PokemonCard class="text-white" :image="pokemon.imageUrl" :name="pokemon.name" :type1="pokemon.type1" />
            </div>
        </div>
    </section>
</template>
<style></style>