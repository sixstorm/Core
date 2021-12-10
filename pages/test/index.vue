<template>
<section>
    <div>
        <h1 v-if="$device.isMobile">MOBILE DETECTED</h1>
    </div>
</section>
</template>

<script>
    export default {
        // layout: (ctx) => ctx.$device.isMobile ? 'mobile' : 'default'
        // async asyncData ({ $content }) {
        //     const movies = await $content('movies/movies').fetch()
        //     return { movies }
        // }
    }
</script>