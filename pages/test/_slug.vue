<template>
    <!-- <article>
        <nuxt-content :document="article" />
    </article> -->
    <div>
      <ul>
      <testComp v-for="article in articles" :key="article.slug" :post="article"></testComp>
      </ul>
    </div>
    
</template>

<script>
export default {
    async asyncData({ $content, params }) {
            const articles = await $content('tech').fetch()

            return { articles }
        },

        head() {
            return {
                title: 'Test - Tech'
            };
        },

        methods: {
            formatDate(date) {
                const options = { year: 'numeric', month: 'long', day: 'numeric' }
            return new Date(date).toLocaleDateString('en', options)
    }
  }
}
</script>

<style>
  .nuxt-content h2 {
    font-weight: bold;
    font-size: 28px;
  }
  .nuxt-content h3 {
    font-weight: bold;
    font-size: 22px;
  }
  .nuxt-content p {
    margin-bottom: 20px;
  }
</style>