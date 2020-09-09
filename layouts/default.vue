<template>
  <v-app class="app">
    <Header />
    <nuxt />
  </v-app>
</template>

<script>
import Header from '@/components/Header.vue';
export default {
}
</script>

<style lang="scss" scoped>
.app {
  background-color: rgb(99, 204, 181);
}
</style>
