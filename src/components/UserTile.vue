<template>
  <article class="w-2/3 mx-auto">
    <section 
      class="md:w-2/3 
            mx-auto 
            bg-white 
            border-gray-200"
    >
      <div class="inline-block lg:mr-12">
        <img
          :src="user.picture.large"
          :alt="`${user.name.first} ${user.name.last} Image`"
          class="rounded-full shadow-xl"
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
  }
}
</script>

<style scoped>
* {
  border: 1px solid red;
}
</style>