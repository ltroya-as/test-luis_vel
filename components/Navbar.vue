<template>
  <div class="p-4 bg-green-700 text-white text-2xl flex justify-between">
    <div>Allan solutions</div>
    <div class="text-xs flex items-center">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-4 w-4"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"
        />
      </svg>

      {{ username }}
    </div>
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
