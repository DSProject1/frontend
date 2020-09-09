<template>
    <div>
        <h1 v-if="postData">{{postData.title}}</h1>
        <p v-if="postData">{{postData.body}}</p>
    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        data() {
            return {
                postData: null,
            }
        },
        async mounted () {
            const {data} = await axios.get(`http://127.0.0.1:3004/posts/${this.$route.params.post}`);
            this.postData = data;
        },
    }
</script>

<style lang="scss" scoped>

</style>