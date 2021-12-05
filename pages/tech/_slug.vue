<template>
    <section>
        <div class="container has-text-centered">
            <h1>Tech Articles</h1>
            <div v-if="Array.isArray(articles)">
                <ul v-for="article of articles" :key="article.slug">
                    <NuxtLink :to="{ name: 'tech-slug', params: { slug: article.slug } }">
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
import showArticle from '../../components/global/showArticle.vue';
    export default {
    components: { showArticle },
        async asyncData({ $content, params }) {
            const articles = await $content('tech', params.slug)
                .sortBy('title')
                .fetch()

            return { articles }
        },

        head() {
            return {
                title: 'Tech'
            }
        }
    }
    // export default {
    //     async asyncData({ $content, params}) {
    //         const articles = await $content('tech', params.slug).fetch()
    //         return { articles }
    //     },

    //     head() {
    //         return {
    //             title: 'Tech'
    //         };
    //     }
    // }
</script>

<style>

</style>