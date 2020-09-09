<template>
    <div>
        <PostForm @createPost="createPost"></PostForm>
    </div>
</template>

<script>
    import PostForm from '@/components/PostForm.vue';
    export default {
        components: {
            PostForm,
        },
        methods: {
            async createPost(post) {
                await this.$axios.$post('http://localhost:3004/posts', {...post})
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>