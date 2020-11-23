<template>
  <ul>
    <li v-for="goal in goals" :key="goal">
      {{ goal }}
    </li>
  </ul>
</template>
<script>
export default {
  data() {
    return {
      goals: ['Finish the course', 'Lern Vue'],
    }
  },
}
</script>
<style scoped>
  ul,li {
    list-style: none
  }
</style>