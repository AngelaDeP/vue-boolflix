<template>
    <li class="card-film">
        <div></div>
        <h3>{{film.title}}</h3>
        <span class="film-date">{{film.release_date}}</span>
        <div>{{film.overview}}</div>
    </li>
</template>

<script>
export default {
    name: 'MyFilmCard',
    props: {
        'film': Object
    }
}
</script>

<style scoped>
@import "../assets/style/card-film-style.scss";
</style>