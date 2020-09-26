<template>
  <header class="sticky-header bg-gray-100">
    <div class="w-2/3 mx-auto lg:pb-8 pb-4">
      <h1 class="text-2xl lg:text-4xl lg:text-left text-center pt-8 mb-4 lg:pt-12 font-semibold lg:inline-block">User Directory</h1>
      <nav class="hidden lg:inline-block text-xl lg:text-2xl font-semibold lg:ml-20 text-center">
       <router-link :to="{ name: 'Home' }">Home</router-link>
       <router-link class="ml-16" :to="{ name: 'Results' }">Users</router-link>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
.sticky-header {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 999;
}
</style>