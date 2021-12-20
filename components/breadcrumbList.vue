<template>
  <div class="container">
    <nav class="breadcrumb has-text-centered-mobile">
      <ul>
        <li><Nuxt-Link to="/">Core</Nuxt-Link></li>
        <li>
          <Nuxt-Link v-bind:to="permalink">{{ parent }}</Nuxt-Link>
        </li>
        <li v-if="$device.isDesktop">
          <Nuxt-Link to="#">{{ article.title }}</Nuxt-Link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  props: ['article', 'parent', 'permalink'],
}
</script>
