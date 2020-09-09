<template>
  <v-container fluid class="my-5">
    <v-row
      align="center"
      justify="center"
      >
      <nuxt-link to="/create">
        <HeroButton></HeroButton>
      </nuxt-link> 
    </v-row>

    <v-row
      align="center"
      justify="center"
    >
      <h1 class="intro display-4">
        Posts
      </h1>
    </v-row>

    <v-row
      class="cards-row"
      dence
      justify="center"
      align="center"
      >
          <v-card v-for="post in posts" @click="openPost(post.id)" :key="post.id" class="text-center ma-2 post-card" max-width="344">
              <v-card-title class="justify-center" style="font-family: 'Poppins';font-style: normal; font-weight: 30; font-size: 140%;">
                {{post.title}}
              </v-card-title>
              <v-card-text style="font-family: 'Poppins';font-style: normal; text-overflow: ellipsis; overflow: hidden; white-space: nowrap;">
                {{post.body}}
              </v-card-text>
          </v-card>
    </v-row>
    
  </v-container>
</template>

<script>
import axios from 'axios';
import HeroButton from '@/components/HeroButton.vue';
export default {
  components: {
    HeroButton,
  },
  data() {
    return {
      posts: []
    }
  },
  async created() {
    try {
      const res = await axios.get(`http://localhost:3004/posts`)

      this.posts = res.data;
    } catch(e) {
      console.error(e)
    }
  },
  methods: {
    openPost(id) {
      this.$router.push(`/${id}`)
    }
  },
}
</script>

<style lang="scss" scoped>
.post-card {
  min-width: 200px;
}
.cards-row {
  margin-top: 30px;
}
</style>
