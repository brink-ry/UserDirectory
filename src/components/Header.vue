<template>
  <header class="sticky-header bg-gray-100">
    <div class="w-2/3 mx-auto pb-8">
      <h1 class="text-2xl lg:text-4xl lg:text-left text-center pt-8 lg:pt-12">User Directory</h1>
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