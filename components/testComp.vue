<template>
<div>
    <ul>
        <a :href="`/blog/${post.slug}`">{{ post.title }}</a>
        <li v-for="tag in post.tags" :key="tag">{{ tag }}</li>
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