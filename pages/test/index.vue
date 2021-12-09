<template>
<div>
    <div v-for="movie in movies" :key="movie.title">
        <listMovies v-bind:movie="movies">
            <p>{{ movie.title }}</p>
        </listMovies>
    </div>
</div>
</template>

<script>
    export default {
        async asyncData ({ $content }) {
            const movies = await $content('movies/movies').fetch()
            return { movies }
        }
    }
</script>