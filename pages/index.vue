<template>
  <div>
    <section>
      <div class="container has-text-centered">
        <img class="pb-6" src="~/assets/minwall.jpg" alt="">
        <h1>Latest Blog Post</h1>
        <ul>
          <li v-for="article of articles" :key="article.slug">
            <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
              <h2>{{ article.title }}</h2>
            </NuxtLink>
          </li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content('blog')
      //   .only(['title'])
      .sortBy('createdat', 'desc')
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
