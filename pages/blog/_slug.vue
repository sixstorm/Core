<template>
    <section>
        <div class="container has-text-centered">
            <h1>Blog Posts</h1>
            <div v-if="Array.isArray(articles)">
                <ul v-for="article of articles" :key="article.slug">
                    <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
                        <h2>{{ article.title }}</h2>
                    </NuxtLink>
                </ul>
            </div>
            <div v-else>
                <show-article v-bind:article="articles"></show-article>
            </div>
        </div>
    </section>
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



