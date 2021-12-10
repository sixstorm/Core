<template>
    <div>
        <section>
            <div class="container">
                <showBC />
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
        sect : function() {
            if(this.dir == "/blog") {
                return 
            }
        },
        blog : function() {
            if(this.dir == "/blog") {
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