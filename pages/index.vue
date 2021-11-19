<template>
  <div class="bg-gray-800 text-white">
    <NuxtLink to="/">Core</NuxtLink>
    <h1 class="p-2.5 text-4xl"><u>Blog Posts</u></h1>
    <br>
    <ul class="flex">
      <li 
        v-for="article of articles" 
        :key="article.slug"
      >
        <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
          <div>
            <h2 class="p-2.5">{{ article.title }}</h2>
            <p>{{ article.description }}</p>
            <p>{{ article.slug }}</p>
            <br>
          </div>
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const articles = await $content('articles')
        .only(['title'])
        .sortBy('createdat', 'asc')
        .fetch()

      return { articles }
    }
  }
</script>
