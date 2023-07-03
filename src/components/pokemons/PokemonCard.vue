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
        <div class="image-container">
            <img :src="image" alt="name" class="img-fluid">
        </div>
        <h4>{{ name }}</h4>
        <div class="type1">{{ type1 }}</div>
    </div>
</template>

<style lang="scss" scoped>
@import 'bootstrap/scss/bootstrap.scss';

.pokemon-card {
    background-color: rgba(255, 255, 255, .15);
    backdrop-filter: blur(5px);
    padding: 20px;
    border-radius: 15px;
}

.image-container {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    overflow: hidden;
    margin: 0 auto;

    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
}

h4 {
    padding-top: 20px;
}
</style>