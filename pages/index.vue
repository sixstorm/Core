<template>
  <div class="is-vcentered has-text-centered">

    <div class="mt-5"><img src="~/assets/minwall.jpg" alt=""></div>
  
    <div>
      <div>
        <h1 class="is-size-4">Latest Blog Post</h1>
        <br />
        <ul>
          <li v-for="article of articles" :key="article.slug">
            <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
              <div>
                <h2>{{ article.title }}</h2>
                <!-- <p>{{ article.description }}</p> -->
                <p>{{ article.description }}</p>
                <br />
              </div>
            </NuxtLink>
          </li>
        </ul>
      </div>

      <div>
        <h2 class="is-size-5">Latest Thought</h2>
        <p class="is-size-6">Rules for Thee, not for me.</p>
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
