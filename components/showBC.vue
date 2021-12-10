<template>
    <div class="container">
        <nav class="breadcrumb has-text-centered-mobile">
            <ul>
                <li><Nuxt-Link to="/">Core</Nuxt-Link></li>
                <li v-if="article.dir =='/blog'"><Nuxt-Link to="/blog">Blog</Nuxt-Link></li>
                <li v-if="article.dir =='/tech'"><Nuxt-Link to="/tech">Tech</Nuxt-Link></li>
                <li v-if="$device.isDesktop"><Nuxt-Link to="#">{{ article.title }}</Nuxt-Link></li>
            </ul>
        </nav>
    </div>
</template>

<script>
export default {
    props: ['article']
}
</script>