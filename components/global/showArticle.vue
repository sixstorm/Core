<template>
    <div>
        <section>
            <div class="container">
                <nav class="breadcrumb">
                    <ul>
                        <li><a href="/">Core</a></li>
                        <li><a href="#">{{ article.title }}</a></li>
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