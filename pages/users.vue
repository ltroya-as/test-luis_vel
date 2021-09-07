<template>
  <div>
    <Navbar />
    <ul v-if="!loading">
      <li v-for="user in users" :key="user.login.uuid">
        {{ user.name.first }} {{ user.name.last }}
      </li>
    </ul>
    <p v-else>Loading...</p>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      users: [],
      loading: false,
    }
  },

  async mounted() {
    try {
      this.loading = true
      const res = await axios.get(
        'https://randomuser.me/api/?results=10&nat=us'
      )
      this.loading = false
      this.users = res.data.results
    } catch (error) {}
  },
}
</script>
