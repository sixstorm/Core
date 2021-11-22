<template>
    <div>
        <article>
            <h1 class="font-sans text-3xl">{{ page.title }}</h1>
            <nuxt-content :document="page" />
        </article>
    </div>
</template>

<script>
export default {
//   head() {
//     return {
//       title: this.title,
//     };
//   },

//   data() {
//     return {
//       title: "Ansible Part 2",
//     };
//   },

  async asyncData({ $content }) {
    const page = await $content("tech/AnsiblePt2").fetch();

    return {
      page,
    };
  },
};
</script>

<style>
    .nuxt-content h1 {
        font-weight: bold;
        font-size: 30px;
    }

    .nuxt-content h3 {
        font-weight: bold;
        font-size: 22px;
    }

    .nuxt-content p {
        margin-bottom: 20px;
    }

    .nuxt-content li {
        padding-left: 10px;
        margin-bottom: 20px;
    }
</style>