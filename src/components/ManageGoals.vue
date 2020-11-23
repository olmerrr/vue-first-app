<template>
  <h2> Manage Goals</h2>
    <input type="text" ref="goal"/>
    <button @click="setGoal">Set Goal</button>
    <error-alert v-if="inputIsInvaliv">
      <h2>Input is invalid</h2>
      <p>If you want to close Error Msg just click on Done</p>
      <button @click="confirmError">Done</button>
      </error-alert>
</template>

<script>
import ErrorAlert from './ErrorAlert.vue';
  export default {
    components: {
      'error-alert': ErrorAlert
    },
    data() {
      return {
        inputIsInvaliv: false,
      }
    },
    methods: {
      setGoal() {
        const enteredValue = this.$refs.goal.value;
        if( enteredValue === ''){
          this.inputIsInvaliv = true;
        }
      },
      confirmError() {
        this.inputIsInvaliv = false;
      }
    }
  }
</script>

