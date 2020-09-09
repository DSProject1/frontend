<template>
    <div class="form-holder">
        <h1>Here you can create a blog post</h1>
        <v-text-field
            v-model="title"
            label="Title"
            solo
            required
        ></v-text-field>
        <v-textarea
            v-model="body"
            solo
            label="Post text"
            rows="8"
            row-height="30"
            no-resize
            required
        ></v-textarea>

        <v-btn class="mr-4" :disabled="disable" @click="submit">submit</v-btn>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                title: '',
                body: '',
            }
        },
        methods: {
            submit() {
                this.$emit("createPost", {
                title: this.title, 
                body: this.body
                })
                this.$router.push("/")
            },
            clear() {
                this.title = '';
                this.body = '';
            }
        },
        computed: {
            disable() {
                if (this.title.length && this.body.length) {
                    return false;
                }
                return true;
            }
        },
    }
</script>

<style lang="scss" scoped>
.form-holder {
    margin: auto;
    width: 60%;
    margin-top: 20vh;
}
h1 {
    margin-bottom: 20px;
}
</style>