<template>
    <div class="bg-gray-800 text-white flex flex-col justify-center items-center h-screen">
        <ul class='flex flex-col text-center'>
            <li v-for="article of articles" :key="article.slug">
                <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
                    <h2 class="p-2.5">{{ article.title }}</h2>
                </NuxtLink>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        async asyncData({ $content, params }) {
            const articles = await $content('blog')
                .sortBy('createdat', 'asc')
                .fetch()
            return { articles }
        }
    }
</script>

<style>

</style>



