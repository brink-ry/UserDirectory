<template>
  <article>
    <UserTile 
      v-for="user in users" 
      :key="user.id.name"
      :user="user"
    />
  </article>
</template>

<script>
import axios from 'axios'
import UserTile from '../components/UserTile.vue'

export default {
  name: 'Results',
  components: {
    UserTile
  },
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