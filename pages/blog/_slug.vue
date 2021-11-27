<template>
    <div>
        <ul>
            <getarticles class="block tile" v-for="article in articles" :key="article.slug" :post="article"></getarticles>
        </ul>
    </div>
</template>

<script>
    export default {
        async asyncData({ $content, params }) {
            const articles = await $content('blog')
                .sortBy('createdat', 'asc')
                .fetch()
            return { articles }
        }
    }
</script>

<style>

</style>



