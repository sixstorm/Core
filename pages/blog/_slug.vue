<template>
    <section>
        <div class="columns is-centered">
            <div class="column is-four-fifths">
                <div v-if="Array.isArray(content)">
                    <h1 class="has-text-centered-mobile">Blog Posts</h1>
                    <ul v-for="article of content" :key="article.slug">
                        <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
                            <h2 class="has-text-centered-mobile">{{ article.title }}</h2>
                        </NuxtLink>
                    </ul>
                </div>
                <div v-else>
                    <breadcrumbList v-bind:article="content" v-bind:title="title" v-bind:permalink="permalink"></breadcrumbList>
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
        data() {
            return {
                title: 'Blog',
                permalink: '/blog',
            }
        }
    }

</script>