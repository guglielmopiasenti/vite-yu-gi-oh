<script>
import PokemonList from './pokemons/PokemonList.vue';
export default {
    components: { PokemonList }
};
</script>
<template>
    <div class="background">
        <div class="container">
            <header>
                <h1 class="text-center py-5">Pokévuex</h1>
            </header>
            <main>
                <PokemonList />
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