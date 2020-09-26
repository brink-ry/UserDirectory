<template>
  <article
    class="w-2/3
          mx-auto
          mb-8"
  >
    <section 
      class="md:w-2/3 
            mx-auto
            py-4
            bg-white 
            border-gray-200"
    >
      <div class="inline-block lg:mr-12">
        <img
          :src="user.picture.large"
          :alt="imageAltTag"
          class="rounded-full 
                shadow-xl
                border-solid
                border-4
                border-gray-700"
        />
      </div>

      <section class="inline-block">
        <p 
          class="text-base 
                md:text-xl"
        ><strong>{{ user.name.first }} {{ user.name.last }}</strong></p>
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
p, section {
  border: 1px solid red;
}
</style>