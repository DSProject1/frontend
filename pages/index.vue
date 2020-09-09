<template>
  <nuxt-link to="/create">
    <HeroButton></HeroButton>
  </nuxt-link>  
</template>

<script>
import HeroButton from '@/components/HeroButton.vue';
export default {
  components: {
    HeroButton,
  },
}
</script>
