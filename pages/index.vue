<template>
  <div>
    <Navbar :username="username" />
    <Dashboard :username="username" />
  </div>
</template>

<script>
export default {
  computed: {
    username() {
      return this.$store.state.store.username
    },
  },
}
</script>
