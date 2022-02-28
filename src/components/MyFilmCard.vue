<template>
    <li class="card-film">
        <div>{{film.title}}</div>
        <div>{{film.release_date}}</div>
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