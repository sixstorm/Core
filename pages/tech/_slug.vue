<template>
    <div>
        <section>
            <div class="columns is-centered">
                <div class="column is-four-fifths">
                    <h1>Tech Articles</h1>
                    <div v-if="Array.isArray(content)">
                        <ul v-for="article of content" :key="article.slug">
                            <NuxtLink :to="{ name: 'tech-slug', params: { slug: article.slug } }">
                                <h2>{{ article.title }}</h2>
                            </NuxtLink>
                        </ul>
                    </div>
                    <div v-else>
                        <div>
                            <nav class="breadcrumb">
                                <ul>
                                    <li><a href="/">Core</a></li>
                                    <li><a href="#">Something</a></li>
                                </ul>
                            </nav>
                        </div>
                        <show-article v-bind:article="content"></show-article>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
import showArticle from '../../components/global/showArticle.vue';
    export default {
    components: { showArticle },
        async asyncData({ $content, params }) {
            const content = await $content('tech', params.slug)
                .sortBy('title')
                .fetch()

            return { content }
        },

        head() {
            return {
                title: 'Tech'
            }
        }
    }
</script>

<style>

</style>