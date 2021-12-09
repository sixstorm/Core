<template>
<section>
    <div class="columns is-centered">
        <div class="column is-four-fifths">
            <h1>Movies I've Watched Recently</h1>
            <showMovies />
        </div>
    </div>
</section>
</template>

<script>
    export default {
        // async asyncData ({ $content }) {
        //     const movies = await $content('movies/movies').fetch()
        //     return { movies }
        // }
    }
</script>