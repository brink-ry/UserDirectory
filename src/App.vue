<template>
  <div 
    id="app" 
    class="container mx-auto bg-gray-100 font-sans"
  >
    <Header/>
    <div id="nav">
      <router-link to="/">Home</router-link> | 
      <router-link to="/results">Results</router-link>
    </div>
    <router-view class="lg:pt-16 pt-8"/>
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

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
