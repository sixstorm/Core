<template>
    <div>
        <p>{{ movie.title }}</p>
        <p>{{ movie.link }}</p>
    </div>
</template>

<script>
    export default {
        props: ['movie']
    }
</script>