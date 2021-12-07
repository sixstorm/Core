<template>
    <section>
        <div class="columns is-centered">
            <div class="column is-four-fifths">
                <h1>Blog Posts</h1>
                <div v-if="Array.isArray(content)">
                    <ul v-for="article of content" :key="article.slug">
                        <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
                            <h2>{{ article.title }}</h2>
                        </NuxtLink>
                    </ul>
                </div>
                <div v-else>
                    <show-article v-bind:article="content"></show-article>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        async asyncData({ $content, params }) {
            const content = await $content('blog', params.slug).fetch()
            return { content }
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



