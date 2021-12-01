<template>
    <div class="is-vcentered has-text-centered is-text-white">
        <ul>
            <h1 class="is-size-2 mt-4 mb-4">
                {{ article.title }}
            </h1>
            <h2 class="is-size-4 mt-4 mb-4">{{ article.description }}</h2>
            <Nuxt-Content class="is-size-5" :document="article" />
        </ul>
    </div>
</template>

<script>
export default {
    props: ['article'],
}
</script>

<style>

</style>