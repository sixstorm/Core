<template>
    <div>
        <div class="bg-gray-800 text-white flex flex-row">
        <div class="bg-gray-800 text-white pt-2 pl-2 flex justify-left">
        <NuxtLink to="/" class="text-4xl p-2.5">Core</NuxtLink>
        </div>
        <div class="bg-gray-800 text-white pt-2 pr-2 flex justify-right">
        <NuxtLink to="/blog" class="text-2xl p-2.5">Blog</NuxtLink>
        </div>
        <div class="bg-gray-800 text-white pt-2 pr-2 flex justify-right">
        <NuxtLink to="/books" class="text-2xl p-2.5">Books</NuxtLink>
        </div>
        <div class="bg-gray-800 text-white pt-2 pr-2 flex justify-right">
        <NuxtLink to="/movies" class="text-2xl p-2.5">Movies</NuxtLink>
        </div>
        <div class="bg-gray-800 text-white pt-2 pr-2 flex justify-right">
        <NuxtLink to="/tech" class="text-2xl p-2.5">Tech</NuxtLink>
        </div>
        <div class="bg-gray-800 text-white pt-2 pr-2 flex justify-right">
        <NuxtLink to="/wiki" class="text-2xl p-2.5">Wiki</NuxtLink>
        </div>
    </div>

    <div class="bg-gray-800 text-white flex flex-col justify-center items-center h-screen">
        <ul class='flex flex-col text-center'>
            <li v-for="article of articles" :key="article.slug">
                <NuxtLink :to="{ name: 'tech-slug', params: { slug: article.slug } }">
                    <h2 class="p-2.5">{{ article.title }}</h2>
                </NuxtLink>
            </li>
        </ul>
    </div>

    </div>
</template>

<script>
    export default {
        async asyncData({ $content, params }) {
            const articles = await $content('tech')
                .sortBy('title')
                .fetch()

            return { articles }
        },

        head() {
            return {
                title: 'Tech'
            };
        }
    }
</script>

<style>

</style>