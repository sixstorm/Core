<template>
    <div>
        <section>
            <div class="container">
                <nav class="breadcrumb">
                    <ul>
                        <li><Nuxt-Link to="/">Core</Nuxt-Link></li>
                        <div v-if="blog" :blog="blog">
                            <li><Nuxt-Link to="/blog">Blog</Nuxt-Link></li>
                        </div>
                        <div v-if="tech" :tech="tech">
                            <li><Nuxt-Link to="/tech">Tech</Nuxt-Link></li>
                        </div>
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
    computed : {
        blog : function() {
            if(this.dir = "/blog") {
                return true
            } else {
                return false
            }
        },
        tech : function() {
            if(this.dir = "/tech") {
                return true
            } else {
                return false
            }
        }
    }
}
</script>

<style>


</style>