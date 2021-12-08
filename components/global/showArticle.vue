<template>
    <div>
        <section>
            <div class="container">
                <nav class="breadcrumb">
                    <ul>
                        <li><Nuxt-Link to="/">Core</Nuxt-Link></li>
                        <li><Nuxt-Link to="#">{{ article.dir }}</Nuxt-Link></li>
                        <li><Nuxt-Link to="#">{{ article.title }}</Nuxt-Link></li>
                    </ul>
                </nav>
                <article>
                    <div class="mb-6">
                        <h1>{{ article.title }}</h1>
                        <h5>{{ article.description }}</h5>
                    </div>
                    <div class="nuxt-content">
                        <Nuxt-Content :document="article" />
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