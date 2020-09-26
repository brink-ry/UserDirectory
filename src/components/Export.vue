<template>
  <div
    @click="clickDownloadLink"
    class="bg-blue-200 w-24 p-2 text-center inline-block download-wrapper"
  >
    <a id="csv-download" :href="downloadLink">Download CSV for Displayed Users</a>
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
  },
  methods: {
    clickDownloadLink () {
      const anchorTarget = document.getElementById('csv-download');
      anchorTarget.click();
    }
  }
}
</script>

<style scoped>
.download-wrapper {
  cursor: pointer;
}
</style>