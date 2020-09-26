<template>
  <header class="sticky-header bg-gray-100">
    <div class="w-2/3 mx-auto pb-4 lg:pb-8">
      <h1 class="text-2xl lg:text-4xl text-center lg:text-left font-semibold pt-8 lg:pt-12 mb-4 lg:inline-block">User Directory</h1>
      <nav class="hidden lg:inline-block text-xl lg:text-2xl text-center font-semibold lg:ml-20">
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