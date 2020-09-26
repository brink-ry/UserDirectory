<template>
  <article class="lg:w-2/3 mx-auto mb-8 bg-blue-700 shadow-2xl rounded-md text-white">
    <section class="lg:w-5/6 mx-auto py-4 flex flex-col lg:flex-row">
      <div class="inline-block mx-auto">
        <img
          :src="user.picture.large"
          :alt="imageAltTag"
          class="rounded"
        />
      </div>

      <section class="inline-block mx-auto lg:text-left text-center">
        <p class="text-base md:text-xl"><strong>{{ user.name.first }} {{ user.name.last }}</strong></p>
        <p>Age: {{ user.dob.age }}</p>
        <p>Gender: {{ user.gender }}</p>
        <p>Email: {{ user.email }}</p>
        <p>Phone: {{ user.phone }}</p>
      </section>
    </section>
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
  computed: {
    imageAltTag () {
      return `${this.user.name.first} ${this.user.name.last} Image`;
    }
  }
}
</script>

<style scoped>
/* p {
  border: 1px solid red;
} */
</style>