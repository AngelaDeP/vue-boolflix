<template>
    <div class="container-sec">
        <ul class="card-list">
            <MyFilmCard v-for="(film, index) in filmCatalogue" :key="index" :film='film'/>
            <MyTvSeriesCard v-for="(series, index) in tvSeriesCatalogue" :key="index" :series='series'/>
        </ul>
    </div>
</template>

<script>
import MyFilmCard from '../components/MyFilmCard.vue';
import MyTvSeriesCard from '../components/MyTvSeriesCard.vue';

export default {
    name: 'MyMain',
    props: {
        'filmCatalogue': Array,
        'tvSeriesCatalogue': Array
    },
    components: {
        MyFilmCard,
        MyTvSeriesCard
    }
}
</script>

<style scoped>
@import "../assets/style/main-style.scss";
</style>