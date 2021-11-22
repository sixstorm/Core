<template>
    <div class="bg-gray-800 text-white pt-2 pl-2">
        <NuxtLink to="/" class="text-4xl p-2.5">Core</NuxtLink>
        <div class="bg-gray-800 text-white flex justify-center items-center h-screen flex-col">
            <ul class="flex">
            <li v-for="article of articles" :key="article.slug">
                <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
                <div>
                    <h2 class="p-2.5">{{ article.title }}</h2>
                    <!-- <p>{{ article.description }}</p> -->
                    <p class="p-2.5">{{ article.slug }}</p>
                    <br />
                </div>
                </NuxtLink>
            </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    async asyncData({ $content, params }) {
        const articles = await $content('articles')
            .sortBy('createdat', 'asc')
            .fetch()

        return { articles }
    }
}
</script>

<style>

</style>