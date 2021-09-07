<template>
  <div>
    <Navbar />
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    // https://randomuser.me/api/?results=10&nat=us
    return {
      users: [],
    }
  },
}
</script>
