<template>
    <li class="card-series">
        <div></div>
        <h3>{{series.name}}</h3>
        <span class="series-date">{{series.first_air_date}}</span>
        <div>{{series.overview}}</div>
    </li>
</template>

<script>
export default {
    name: 'MyTvSeriesCard',
    props: {
        'series': Object
    }
}
</script>

<style scoped>
@import "../assets/style/card-series-style.scss";
</style>