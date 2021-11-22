<script>
    export default {
        async asyncData({ $content, params }) {
            const techArticles = await $content('tech', params.slug).fetch()
            return { techArticles }
        }
    }
</script>

<template>
    <div class="bg-gray-800 text-white flex flex-col justify-center items-center h-screen">
        <article>
            <h1 class="p-1.5">{{ techArticle.title }}</h1>
            <h3 class="p-1.5">{{ techArticle.description }}</h3>
            <Nuxt-Content :document="techArticle" />
            <p>Last updated: {{ techArticle.updatedAt }}</p>
            <p>teamtuck</p>
        </article>
    </div>
</template>

<style>
    .nuxt-content h1 {
        font-weight: bold;
        font-size: 28px;
    }

    .nuxt-content h3 {
        font-weight: bold;
        font-size: 22px;
    }

    .nuxt-content p {
        margin-bottom: 20px;
    }
</style>