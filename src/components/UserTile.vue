<template>
  <article>
    <section class="img-wrapper">
      <img
        :src="user.picture.large"
        :alt="`${user.name.first} ${user.name.last} Image`"
      />
    </section>

    <section>
      <p><strong>{{ user.name.first }} {{ user.name.last }}</strong></p>
      <p>Age: {{ user.dob.age }}</p>
      <p>Gender: {{ user.gender }}</p>
      <p>Email: {{ user.email }}</p>
      <p>Phone: {{ user.phone }}</p>
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
