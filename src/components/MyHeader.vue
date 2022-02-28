<template>
    <header>
        <div class="logo">
            <h1>BOOLFIX</h1>
        </div>
        <form>
            <input class="search-text" type="text" v-model="searchText">
            <button type="submit" @click.prevent="$emit('search', searchText)">Ricerca</button>
        </form>
    </header>   
</template>

<script>
export default {
    name: 'MyHeader',
    data() {
        return {
            searchText: ''
        }
    }
}
</script>

<style scoped>
@import "../assets/style/header-style.scss";
</style>