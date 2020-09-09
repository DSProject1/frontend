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
            createPost(post) {
                console.log(post);
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>