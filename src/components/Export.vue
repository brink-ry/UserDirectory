<template>
  <div>
    <a :href="downloadLink">download CSV</a>
  </div>
</template>

<script>
export default {
  name: 'Export',
  props: {
    page: {
      type: Number,
      required: true
    }
  },
  computed: {
    downloadLink () {
      return `https://randomuser.me/api/?page=${this.page}&results=10&seed=MST&format=csv&dl`
    }
  }
}
</script>