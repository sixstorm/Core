<template>
    <div class="columns">
        <div class="column is-half has-text-centered" v-for="video in videos" :key="video.title">
            <p>{{ video.title }}</p>
            <figure class="image is-16by9">
                <iframe class="has-ratio" width="560" height="315" v-bind:src="video.link" frameborder="0"></iframe>
            </figure>
        </div>
    </div>
</template>

<script>
    import data from "~/content/videos/videos.json";
    
    export default {
        data() {
            return {
                videos: data,
            }
        }
    }
</script>
