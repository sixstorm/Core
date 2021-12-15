<template>
  <nav class="navbar">
    <div class="navbar-brand">
      <Nuxt-Link
        to="/"
        class="navbar-item pr-6"
        @click.native="isHamburgerOpen = !isHamburgerOpen"
        >Core</Nuxt-Link
      >
      <a
        name="burger-menu"
        role="button"
        class="navbar-burger burger"
        :class="{ 'is-active': isHamburgerOpen }"
        @click="isHamburgerOpen = !isHamburgerOpen"
      >
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div class="navbar-menu" :class="{ 'is-active': isHamburgerOpen }">
      <div class="navbar-end">
        <Nuxt-Link
          to="/tech"
          class="navbar-item pr-6"
          @click.native="isHamburgerOpen = !isHamburgerOpen"
          >Tech</Nuxt-Link
        >
        <Nuxt-Link
          to="/blog"
          class="navbar-item pr-6"
          @click.native="isHamburgerOpen = !isHamburgerOpen"
          >Blog</Nuxt-Link
        >
        <Nuxt-Link
          to="/movies"
          class="navbar-item pr-6"
          @click.native="isHamburgerOpen = !isHamburgerOpen"
          >Movies</Nuxt-Link
        >
        <Nuxt-Link
          to="/books"
          class="navbar-item pr-6"
          @click.native="isHamburgerOpen = !isHamburgerOpen"
          >Books</Nuxt-Link
        >
        <Nuxt-Link
          to="/music"
          class="navbar-item pr-6"
          @click.native="isHamburgerOpen = !isHamburgerOpen"
          >Music</Nuxt-Link
        >
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isHamburgerOpen: false,
    }
  },
}
</script>

<!--
<template>
  <nav class="level navbar is-spaced">
    <div class="level-left has-text-centered">
      <a class="level-item navbar-item" href="/">Core</a>
    </div>
    <div class="level-right has-text-centered">
      <a class="level-item navbar-item" href="/tech">Tech</a>
      <a class="level-item navbar-item" href="/blog">Blog</a>
      <a class="level-item navbar-item" href="/movies">Movies</a>
      <a class="level-item navbar-item" href="/books">Books</a>
      <a class="level-item navbar-item" href="/music">Music</a>
    </div>
  </nav>
</template>
-->
