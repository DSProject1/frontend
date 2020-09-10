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
                await this.$axios.$post('http://127.0.0.1:80/post', {...post})
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>