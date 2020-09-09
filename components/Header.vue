<template>
    <div>
        <v-app-bar :elevation="3" color="white" elevate-on-scroll>
        <nuxt-link to="/" class="title">Project</nuxt-link>
        </v-app-bar>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.title {
    text-decoration: none;
    color: black;
}
</style>