<template>
    <div>
        <table>
            <thead>
                <tr>
                    <th>Title</th>
                    <th>Link</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, key) of movies" :key="key">
                    <td>{{ item.title }}</td>
                    <td><a href="{{ item.link }}">IMDB</a></td>
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