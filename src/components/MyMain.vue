<template>
    <div class="container-sec">
        <ul class="card-list">
            <MyFilmCard v-for="(film, index) in filmCatalogue" :key="index" :film='film'/>
        </ul>
    </div>
</template>

<script>
import MyFilmCard from '../components/MyFilmCard.vue';

export default {
    name: 'MyMain',
    props: {
        'filmCatalogue': Array
    },
    components: {
        MyFilmCard
    }
}
</script>

<style scoped>
@import "../assets/style/main-style.scss";
</style>