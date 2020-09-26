<template>
  <article>
    <UserTile 
      v-for="user in users" 
      :key="user.login.username"
      :user="user"
    />

    <section>
      <Pagination
        @next-page-event="getNextPage"
        @previous-page-event="getPreviousPage"
        :isDisabledPreviousPage="isDisabledPreviousPage"
      />
    </section>
  </article>
</template>

<script>
import axios from 'axios'
import UserTile from '@/components/UserTile.vue'
import Pagination from '@/components/Pagination.vue'

export default {
  name: 'Results',
  components: {
    UserTile,
    Pagination
  },
  data () {
    return {
      page: 1,
      users: []
    }
  },
  methods: {
    async getNextPage () {
      this.page += 1;
      await this.getUsers();
    },
    async getPreviousPage () {
      this.page -= 1;
      if ( this.page <= 0 ) this.page = 1;

      await this.getUsers();
    },

    async getUsers () {
      try {

        const { data: { results } } = await axios.get(`https://randomuser.me/api/?page=${this.page}&results=10&seed=MST`);

        this.users = results;
      } catch ( error ) {
        throw error;
      }
    }
  },
  computed: {
    isDisabledPreviousPage () {
      return this.page == 1;
    }
  },
  async created () {
    await this.getUsers();
  }
}
</script>