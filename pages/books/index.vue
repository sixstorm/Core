<template>
  <section>
    <div class="columns is-centered">
      <div class="column is-four-fifths">
        <h1 class="has-text-centered-mobile">Books I've Read Lately</h1>
        <showBooks />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  head() {
    return {
      title: 'Books',
    }
  },
}
</script>
