<template>
  <div>
    <nav class="text-center mb-8">
      <button 
        @click="prevPage"
        :disabled="isDisabledPreviousPage"
        class="mr-8 lg:mr-32"
      >Previous</button>

      <button 
        @click="nextPage"
        class="ml-8 lg:ml-32"
        >Next</button>
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
    // Emit custom events for page navigation.
    // These will be caught by the parent component, which updates the page number.
    nextPage () {
      this.$emit( 'next-page-event' );
    },
    prevPage () {
      this.$emit( 'previous-page-event' );
    }
  }
}
</script>

<style scoped>
button {
  border: 1px solid gray;
  border-radius: 0.5rem;
  cursor: pointer;
  color: white;
  background: #2b6cb0;
  padding: 4px;
  width: 75px;
}

button:disabled {
  cursor: not-allowed;
}
</style>