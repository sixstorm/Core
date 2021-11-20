<script>
    export default {
        async asyncData({ $content, params }) {
            const article = await $content('articles', params.slug).fetch()
            // const tagList = await $content('tags')
                // .only(['name','slug'])
                // .where({ name: { containsAny: article.tags } })
                // .fetch()
            // const tags = Object.assign({}, ...tagList.map((s) => ({ [s.name]: s })))
            return { article }
        }
    }
</script>

<template>
    <div class="bg-gray-800 text-white flex flex-col justify-center items-center h-screen">
        <article>
            <h1 class="p-1.5">{{ article.title }}</h1>
            <h3 class="p-1.5">{{ article.description }}</h3>
            <!-- <h3 class="p-1.5">{{ article.tags }}</h3> -->
            <nuxt-content :document="article" />
            <p>Last updated: {{ article.updatedAt }} </p>
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



