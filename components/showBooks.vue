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
                <tr v-for="book in books" :key="book.title">
                    <td>{{ book.title }}</td>
                    <td><a v-bind:href="book.link">Amazon</a></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    import data from "~/content/books/books.json";

    export default {
        data() {
            return {
               books: data, 
            }
        }
    }
</script>