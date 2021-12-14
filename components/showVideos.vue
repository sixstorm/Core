<template>
    <div class="container">
        <div class="content" v-for="video in videos" :key="video.title">
        <ul>
            <li class="has-centered-text-mobile"><a v-bind:href="video.link">{{ video.title }}</a></li>
        </ul>
        </div>
    </div>
</template>

<script>
    import data from "~/content/videos/videos.json"
    export default {
        data() {
            return {
                videos: data,
            }
        }
    }
</script>
