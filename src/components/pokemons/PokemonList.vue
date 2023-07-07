<script>
import PokemonCard from './PokemonCard.vue';
import { store } from '../../assets/data/store.js';
import SearchForm from './SearchForm.vue';
export default {
    components: { PokemonCard, SearchForm },
    data() {
        return { store: store }
    },
    emits: ['type-change'],
    methods: {
        onOptionChange(type) {
            this.$emit('type-change', type);
        }
    }
};
</script>
<template>
    <SearchForm defaultLabel="All types" :options="store.types" @option-change="onOptionChange" />
    <section id="pokemons">
        <!-- Creating a row with columns for each Pokemon -->
        <div class="row g-4 row-cols-2 row-cols-md-3 row-cols-lg-4">
            <!-- Looping through each Pokemon in the 'store.pokemons' array -->
            <div class="col" v-for="pokemon in store.pokemons" :key="pokemon.id">
                <!-- Rendering the PokemonCard component for each Pokemon -->
                <PokemonCard class="text-white" :image="pokemon.imageUrl" :name="pokemon.name" :type1="pokemon.type1" />
            </div>
        </div>
    </section>
</template>
<style></style>