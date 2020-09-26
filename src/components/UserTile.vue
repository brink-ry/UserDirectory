<template>
  <article>
    <p>{{ user.name.first }} {{ user.name.last }}</p>
  </article>
</template>

<script>
export default {
  name: 'UserTile',
  props: {
    user: {
      type: Object,
      required: true
    }
  },
  data () {
    return {

    }
  },
  created () {
    console.log(`created tile for ${this.user.name.first} ${this.user.name.last}`)
  }
}
</script>
