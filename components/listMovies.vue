<template>
    <div>
        <div v-for="movie in movies" :key="movie.title">
            <p>{{ movie.title }}</p>
            <p>{{ movie.link }}</p>
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