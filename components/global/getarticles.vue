<template>
<div>
    <ul class="bg-gray-800 text-white flex flex-col justify-center">
        <h2 class="bg-gray-800 text-white text-xl"><a :href="`/blog/${post.slug}`">{{ post.title }}</a></h2>
        <p class="bg-gray-800 text-white">{{ post.description }}</p>
        <!-- <li v-for="tag in post.tags" :key="tag">{{ tag }}</li> -->
    </ul>
</div>
</template>

<script>
export default {
    props: {
        post: Object,
    }
}
</script>