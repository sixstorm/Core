<template>
    <div class="is-vcentered has-text-centered">
        <div v-if="Array.isArray(articles)">
            <div class="column">
                <ul v-for="article of articles" :key="article.slug">
                    <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
                        <h2 class="is-size-4">{{ article.title }}</h2>
                    </NuxtLink>
                </ul>
            </div>
        </div>
        <div v-else>
            <show-article v-bind:article="articles"></show-article>
        </div>
    </div>
</template>

<script>
    export default {
        async asyncData({ $content, params }) {
            const articles = await $content('blog', params.slug).fetch()
            return { articles }
        },
        head() {
            return {
                title: 'Blog'
            }
        }
    }

</script>

<style>

</style>



