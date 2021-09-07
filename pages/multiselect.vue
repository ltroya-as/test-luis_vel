<template>
  <div>
    <Navbar />

    <div class="p-5">
      <h2>Total Score: {{ totalScore }}</h2>
      <h2>Max Score: {{ maxScore }}</h2>
      <h2>Min Score: {{ minScore }}</h2>
      <h2>Top student name: {{ topStudent }}</h2>
      <h2>Worst student name: {{ worstStudent }}</h2>

      <div class="mt-10">
        <multiselect
          v-model="selected"
          :options="options"
          track-by="name"
          label="name"
          placeholder="Select a person"
          class="border border-indigo-500 p-2"
        >
        </multiselect>
      </div>
    </div>
  </div>
</template>

<script>
import Multiselect from 'vue-multiselect'

export default {
  components: { Multiselect },
  data() {
    return {
      selected: null,
      students: [
        { first: 'Vicky', lastname: 'Morales', score: 10 },
        { first: 'James', lastname: 'Williams', score: 20 },
        { first: 'Vicky', lastname: 'Lee', score: 5 },
        { first: 'Vicky', lastname: 'Sanchez', score: 2 },
      ],
    }
  },

  computed: {
    options() {
      return []
    },

    totalScore() {
      return 0
    },

    maxScore() {
      return 0
    },

    minScore() {
      return 0
    },
    topStudent() {
      return 'Name'
    },

    worstStudent() {
      return 'Name'
    },
  },
}
</script>

