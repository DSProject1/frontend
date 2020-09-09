<template>
  <v-app>
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
      <v-card class="d-flex align-content-center flex-wrap transparent" flat>
        <h1 class="intro display-4">
          Posts
        </h1>
      </v-card>
    </v-row>
    <v-row 
      align="center"
      justify="center"
      >
      <v-card
        class="d-flex align-content-center transparent"
        flat
        min-height="200"
        >
        <v-flex xs12 sm6 md4 lg4 v-for="post in posts" :key="post.id">
          <v-card class="text-center ma-2 " max-width="344" color="#241663">
            <v-card-title class="justify-center" style="font-family: 'Poppins';font-style: normal;color: #EFFFFF; font-weight: 30; font-size: 140%;">
              {{post.title}}
            </v-card-title>
            <v-card-text style="font-family: 'Poppins';font-style: normal;color: #EFFFFF;">
              {{post.body}}
            </v-card-text>
          </v-card>
        </v-flex>
      </v-card>
    </v-row>
  </v-container>
  </v-app>
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
}
</script>
