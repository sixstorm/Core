<template>
  <div>
    <section>
      <div class="columns is-centered">
        <div class="column is-four-fifths">
          <div v-if="Array.isArray(content)">
            <h1 class="has-text-centered-mobile">Tech Articles</h1>
            <ul v-for="article of content" :key="article.slug">
              <NuxtLink
                :to="{ name: 'tech-slug', params: { slug: article.slug } }"
              >
                <h2 class="has-text-centered-mobile">{{ article.title }}</h2>
              </NuxtLink>
            </ul>
          </div>
          <div v-else>
            <breadcrumbList
              v-bind:article="content"
              v-bind:parent="parent"
              v-bind:title="title"
              v-bind:permalink="permalink"
            ></breadcrumbList>
            <show-article v-bind:article="content"></show-article>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const content = await $content('tech', params.slug).sortBy('title').fetch()
    return { content }
  },
  data() {
    return {
      parent: 'Tech',
      permalink: '/tech',
    }
  },
}
</script>
