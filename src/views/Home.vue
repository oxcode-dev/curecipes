<template>
  <div class="home">
    <Header />
    <Hero />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Hero from '@/components/Hero.vue'
import Header from '@/components/Header.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld, Hero, Header
  }
}
</script>
