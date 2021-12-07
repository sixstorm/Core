<template>
    <div class="container">
        <nav class="navbar" role="navigation" aria-label="main navigation">
            <div class="navbar-brand">
                <Nuxt-Link to="/" class="navbar-item pr-6">Core</Nuxt-Link>
                <a
                  name="burger-menu"
                  role="button"
                  class="navbar-burger"
                  @click="showNav = !showNav"
                  :class="{ 'is-active': showNav }"
                >
                  <span aria-hidden="true"></span>
                  <span aria-hidden="true"></span>
                  <span aria-hidden="true"></span>
                </a>
            </div>

            <div class="navbar-menu" :class="{ 'is-active': showNav }">
                <div class="navbar-start">
                    <Nuxt-Link
                        v-for="(item, key) of items"
                        :key="key"
                        class="navbar-item"
                        :to="item.to"
                    >{{ item.title }}</Nuxt-Link>
                </div>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    data() {
        return {
            showNav: false,
            items: [
                {
                    title: "Tech",
                    icon: "tech",
                    to: { name: "/tech" },
                },
                {
                    title: "Blog",
                    icon: "blog",
                    to: { name: "/blog" },
                },
                {
                    title: "Movies",
                    icon: "Movies",
                    to: { name: "movies" },
                },
                {
                    title: "Books",
                    icon: "Books",
                    to: { name: "books" },
                },
            ]
        }
    }
}
</script>