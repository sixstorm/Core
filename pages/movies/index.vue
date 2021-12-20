<template>
  <section>
    <div class="columns is-centered">
      <div class="column is-four-fifths">
        <h1 class="has-text-centered-mobile">Movies I've Watched Recently</h1>
        <ShowMovies />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  head() {
    return {
      title: 'Movies',
    }
  },
}
</script>
