<template>
  <div>
    <section>
      <div class="columns is-centered">
        <div class="column is-four-fifths">
          <!-- <img src="~/assets/minwall2.jpg" alt=""> -->
          <h1 class="has-text-centered-mobile">Latest Blog Post</h1>
        <ul>
          <li v-for="article of articles" :key="article.slug">
            <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
              <h2 class="has-text-centered-mobile">{{ article.title }}</h2>
            </NuxtLink>
          </li>
        </ul>
        </div>
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
