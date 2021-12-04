<template>
    <div>
        <section>
            <div class="container">
                <div class="content">
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