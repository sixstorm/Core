<template>
    <div>
        <h1 class="is-centered">MOVIES!</h1>
        <table class="table is-bordered is-hoverable is-fullwidth">
            <thead>
                <tr>
                    <th style="text-align:left">Title</th>
                    <th style="text-align:left">Link</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, key) of movies" :key="key">
                    <td>{{ item.title }}</td>
                    <td><a href="#">{{ item.link }}</a></td>
                </tr>
            </tbody>
        </table>
        <!-- <ul v-for="(item, key) of movies" :key="key">{{ item.title }}</ul> -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            movies: [
                {
                    title: "Home Alone",
                    link: "https://www.imdb.com/title/tt0099785/"
                },
                {
                    title: "Harry Potter and the Sorcerer's Stone",
                    link: "https://www.imdb.com/title/tt0241527/"
                },
                {
                    title: "Cruella",
                    link: "https://www.imdb.com/title/tt3228774/"
                }
            ],
        }
    }
}
</script>