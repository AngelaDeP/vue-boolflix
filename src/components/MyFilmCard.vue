<template>
    <li class="card-film">
        <h3>{{film.title}}</h3>
        <img class="film-poster" :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`" alt="">
        <span class="film-date">{{film.release_date}}</span>
        <div class="flag-sec">
            <img class="flag" v-if="languages.includes(film.original_language)" :src="require('.././assets/flag-languages/' + film.original_language + '.png')" >
            <span v-else>{{film.original_language}}</span>
        </div>
        <div class="vote-sec">
            {{film.vote_average}}
        </div>
        <div>{{film.overview}}</div>
    </li>
</template>

<script>
export default {
    name: 'MyFilmCard',
    props: {
        'film': Object
    },
    data() {
        return {
            languages: [ 'en', 'it'],
        }
    },
}
</script>

<style scoped>
@import "../assets/style/card-film-style.scss";
</style>