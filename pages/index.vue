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

  <div class="bg-gray-800 text-white flex justify-center items-center h-screen flex-row">
    <div class="flex flex-col p-3">
      <h1 class="p-2.5 text-4xl"><u>Latest Blog Post</u></h1>
      <br />
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

    <div class="flex flex-col p-5">
      <h2>Latest Thought</h2>
      <p>Something should go here...</p>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content('blog')
      //   .only(['title'])
      .sortBy('createdat', 'asc')
      .limit(1)
      .fetch()

    return { articles }
  },

  head() {
            return {
                title: 'Core'
            };
        }
}
</script>
