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
        props: ['movie']
    }
</script>