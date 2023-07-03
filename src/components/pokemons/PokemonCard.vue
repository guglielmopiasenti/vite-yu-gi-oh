<script>
export default {
    props: {
        image: String,
        name: String,
        number: Number,
        type1: String,
        type2: String,
    }

}
</script>
<template>
    <div class="pokemon-card text-center">
        <img :src="image" alt="name" class="img-fluid">
        <h4>{{ name }}</h4>
        <div class="type1">{{ type1 }}</div>
        <div class="type2">{{ type2 }}</div>
    </div>
</template>
<style lang="scss" scoped>
img {
    height: 80px;
}
</style>