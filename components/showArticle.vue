<template>
    <div>
        <section>
            <div class="container">
                <nav class="breadcrumb">
                    <ul>
                        <li v-if="$device.isDesktop"><Nuxt-Link to="/">Core</Nuxt-Link></li>
                        <li v-if="$device.isDesktop"><Nuxt-Link to="#">{{ article.dir }}</Nuxt-Link></li>
                        <li v-if="$device.isDesktop"><Nuxt-Link to="#">{{ article.title }}</Nuxt-Link></li>
                    </ul>
                </nav>
                <article>
                    <div class="mb-6">
                        <h1 class="has-text-centered-mobile">{{ article.title }}</h1>
                        <h5 class="has-text-centered-mobile">{{ article.description }}</h5>
                    </div>
                    <div class="nuxt-content has-text-centered-mobile">
                        <Nuxt-Content class="is-size-5-mobile" :document="article" />
                    </div>
                </article>
            </div>
        </section>
    </div>
</template>

<script>
export default {
    props: ['article'],
}
</script>

<style>


</style>