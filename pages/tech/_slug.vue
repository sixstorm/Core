<template>
    <div class="is-vcentered has-text-centered mt-4 p-4">
        <div v-if="Array.isArray(articles)">
            <ul v-for="article of articles" :key="article.slug">
                <NuxtLink :to="{ name: 'tech-slug', params: { slug: article.slug } }">
                    <h2 class="is-size-4">{{ article.title }}</h2>
                </NuxtLink>
            </ul>
        </div>
        <div v-else>
            <show-article v-bind:article="articles"></show-article>
        </div>
    </div>
</template>

<script>
    export default {
        async asyncData({ $content, params }) {
            const articles = await $content('tech', params.slug)
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