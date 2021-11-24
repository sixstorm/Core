<template>
<div>
    <ul>
        <a :href="`/blog/${post.slug}`"></a>
        <li v-for="tag in post.tag" :key="tag">{{ tag }}</li>
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