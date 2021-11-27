<template>
<div>
    <ul>
        <h2><a :href="`/blog/${post.slug}`">{{ post.title }}</a></h2>
        <p>{{ post.description }}</p>
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