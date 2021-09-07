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
      return this.students.map((student) => ({
        name: student.first + ' ' + student.lastname,
      }))
    },

    totalScore() {
      let total = 0

      this.students.forEach((student) => {
        total += student.score
      })

      return total
    },

    maxScore() {
      const scores = this.students.map((student) => student.score)
      return Math.max(...scores)
    },

    minScore() {
      const scores = this.students.map((student) => student.score)
      return Math.min(...scores)
    },

    topStudent() {
      const topStudent = this.students.find(
        (student) => student.score === this.maxScore
      )

      return `${topStudent.first} ${topStudent.lastname}`
    },

    worstStudent() {
      const worstStudent = this.students.find(
        (student) => student.score === this.minScore
      )

      return `${worstStudent.first} ${worstStudent.lastname}`
    },
  },
}
</script>
