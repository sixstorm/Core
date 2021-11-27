<template>
    <div>
        <ul>
            <li v-for="article of articles" :key="article.slug">
                <NuxtLink :to="{ name: 'tech-slug', params: { slug: article.slug } }">
                    <h2>{{ article.title }}</h2>
                </NuxtLink>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        async asyncData({ $content, params }) {
            const articles = await $content('tech')
                .sortBy('title')
                .fetch()

            return { articles }
        },

        head() {
            return {
                title: 'Tech'
            };
        }
    }
</script>

<style>

</style>