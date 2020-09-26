<template>
  <div 
    id="app" 
    class="container mx-auto bg-gray-100 font-sans"
  >
    <Header/>
    
    <router-view class="pt-48"/>

    <Footer/>
  </div>
</template>

<script>
import Footer from '@/components/Footer.vue'
import Header from '@/components/Header.vue'

export default {
  name: 'App',
  components: {
    Footer,
    Header
  }
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
