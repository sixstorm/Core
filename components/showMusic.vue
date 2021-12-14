<template>
  <div>
    <table
      class="table is-bordered is-narrow is-hoverable is-fullwidth is-size-5"
    >
      <thead>
        <tr>
          <th style="text-align: left">Title</th>
          <th style="text-align: left">Artist</th>
          <th style="text-align: left">Link</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="song in music" :key="song.title">
          <td>{{ song.title }}</td>
          <td>{{ song.artist }}</td>
          <td>
            <a v-bind:href="song.link">{{ song.type }}</a>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import data from '~/content/music/music.json'

export default {
  data() {
    return {
      music: data,
    }
  },
}
</script>
