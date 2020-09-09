<template>
    <v-container>
        <div class="wrapper">
            <h1 v-if="postData">{{postData.title}}</h1>
            <p v-if="postData">{{postData.body}}</p>
        </div>
    </v-container>
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
.wrapper {
    padding: 50px;
    background-color: white;
    border-radius: 20px;
    margin-top: 10vh;
    box-shadow: 1px 1px 10px;
}
h1 {
    text-align: center;
}
p {
    padding: 30px;
    overflow-wrap: break-word;
}
</style>