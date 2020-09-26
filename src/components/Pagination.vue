<template>
  <div>
    <nav>
      <button :disabled="isDisabledPreviousPage">Previous</button>

      <button>Next</button>
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
}
</script>