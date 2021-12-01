<template>
    <div>
        <div v-if="Array.isArray(articles)">
            <li v-for="article of articles" :key="article.slug">
                <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
                    <h2>{{ article.title }}</h2>
                </NuxtLink>
            </li>
        </div>
        <div v-else>
            <show-article v-bind:article="articles"></show-article>
            <!-- <ul>
                <getarticles class="block tile" v-for="article in articles" :key="article.slug" :post="article"></getarticles>
            </ul> -->
        </div>
    </div>
</template>

<script>
import showArticle from '~/components/global/showArticle.vue'
    export default {
        async asyncData({ $content, params }) {
            const articles = await $content('blog', params.slug).fetch()
            return { articles }
        },
    }
</script>

<style>

</style>



