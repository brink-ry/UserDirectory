<template>
  <article>
    <div v-for="user in users" :key="user.id.name">
      <p>{{ user.name.first }} {{ user.name.last }}</p>
    </div>
  </article>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Results',
  data () {
    return {
      page: 1,
      users: []
    }
  },
  methods: {
    async getUsers () {
      // TODO: put this in a try/catch block in case API call fails
      const { data: { results } } = await axios.get(`https://randomuser.me/api/?page=${this.page}&results=10&seed=MST`);

      this.users = results;
      console.log(this.users)
    }
  },
  async created () {
    await this.getUsers();
  }
}
</script>