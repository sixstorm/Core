<template>
  <div class="is-flex is-flex-direction-column is-justify-content-center is-align-content-center">
  
    <div>
      <div>
        <h1><u>Latest Blog Post</u></h1>
        <br />
        <ul>
          <li v-for="article of articles" :key="article.slug">
            <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
              <div>
                <h2>{{ article.title }}</h2>
                <!-- <p>{{ article.description }}</p> -->
                <p>{{ article.slug }}</p>
                <br />
              </div>
            </NuxtLink>
          </li>
        </ul>
      </div>

      <div>
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
