<template>
  <article>
    <section class="flex lg:flex-row flex-col">

    <Export :page="page"/>

      <section class="lg:w-full mx-auto">
        <UserTile 
          v-for="user in users" 
          :key="user.login.uuid"
          :user="user"
        />
      </section>
    </section>

    <section>
      <!-- Using custom events emitted from Pagination component to watch for prev/next. -->
      <Pagination
        @next-page-event="getNextPage"
        @previous-page-event="getPreviousPage"
        :isDisabledPreviousPage="isDisabledPreviousPage"
      />
    </section>

    <p class="text-center"><strong>Page {{ page }}</strong></p>
  </article>
</template>

<script>
import axios from 'axios'
import UserTile from '@/components/UserTile.vue'
import Pagination from '@/components/Pagination.vue'
import Export from '@/components/Export.vue'

export default {
  name: 'Results',
  components: {
    UserTile,
    Pagination,
    Export
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
      const { data: { results } } = await axios.get(`https://randomuser.me/api/?page=${ this.page }&results=10&seed=MST`);

      this.users = results;
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