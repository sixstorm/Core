<template>
    <div>
        <ul>
            <h1 class="is-size-2">
                {{ article.title }}
            </h1>
            <h2 class="is-size-4">{{ article.description }}</h2>
            <Nuxt-Content class="content is-medium is-vcentered mt-5" :document="article" />
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