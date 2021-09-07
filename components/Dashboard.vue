<template>
  <div class="flex h-screen">
    <div class="p-4 bg-indigo-500 text-white">
      Sidebar
      <div class="mt-4">Hello, {{ username }}</div>
    </div>
    <div class="flex-1 p-4">Here is the content</div>
  </div>
</template>

<script>
export default {
  props: {
    username: {
      type: String,
      default: 'Anonymous',
    },
  },
}
</script>
