<template>
  <article
    class="w-2/3
          mx-auto
          mb-8"
  >
    <section 
      class="lg:w-5/6
            mx-auto
            py-4
            bg-blue-200
            border-solid
            border-2
            border-gray-700
            flex
            flex-col
            lg:flex-row"
    >
      <div 
        class="inline-block
              mx-auto"
      >
        <img
          :src="user.picture.large"
          :alt="imageAltTag"
          class="rounded-full 
                shadow-xl
                border-solid
                border-4
                border-gray-500"
        />
      </div>

      <section 
        class="inline-block
              mx-auto
              lg:text-right
              text-center"
      >
        <p 
          class="text-base 
                md:text-xl
                lg:text-left"
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
/* p {
  border: 1px solid red;
} */
</style>