<template>
  <div>
    <nav>
      <button 
        @click="prevPage"
        :disabled="isDisabledPreviousPage"
      >Previous</button>

      <button @click="nextPage">Next</button>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'Pagination',
  props: {
    isDisabledPreviousPage: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    // Emit custom events for page navigation
    // These will be caught by the parent component, which keeps track of the page #
    nextPage () {
      this.$emit( 'next-page-event' );
    },
    prevPage () {
      this.$emit( 'previous-page-event' );
    }
  }
}
</script>