<template>
    <div>
        <table class="table is-bordered is-narrow is-hoverable is-fullwidth is-size-5">
            <thead>
                <tr>
                    <th style="text-align:left">Title</th>
                    <th style="text-align:left">Link</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="movie in movies" :key="movie.title">
                    <td>{{ movie.title }}</td>
                    <td><a v-bind:href="movie.link">IMDB</a></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    import data from "~/content/movies/movies.json";

    export default {
        data() {
            return {
               movies: data, 
            }
        }
    }
</script>
