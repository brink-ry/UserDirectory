<template>
  <div
    @click="clickDownloadLink"
    class="bg-blue-200 lg:w-24 lg:fixed lg:h-24 mx-auto mb-4 lg:mt-8 p-2 rounded text-center cursor-pointer"
  >
    <a 
      id="csv-download" 
      :href="downloadLink"
    >Export Page to CSV</a>
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
