<template>
    <div>
        <article>
            <h1>{{ page.title }}</h1>
            <nuxt-content :document="page" />
        </article>
    </div>
</template>

<script>
export default {
  head() {
    return {
      title: this.title,
    };
  },

//   data() {
//     return {
//       title: "Ansible Part 2",
//     };
//   },

  async asyncData({ $content }) {
    const page = await $content("tech/testmd").fetch();

    return {
      page,
    };
  },
};
</script>

<style>
</style>