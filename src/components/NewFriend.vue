<template>
  <form @submit.prevent="submitData">
    <div>
      <input type="text" v-model="enteredName" placeholder="Name: "/>
    </div>

    <div>
      <input type="tel" v-model="enteredPhone" placeholder="Phone: "/>
    </div>

    <div>
      <input type="email" v-model="enteredEmail" placeholder="E-mail: "/>
    </div>

    <div>
      <button>Add Contact</button>
    </div>
  </form>
</template>
<script>
export default {
  emits: ['add-contact'],
  data() {
    return {
      enteredName: '',
      enteredPhone: '',
      enteredEmail: ''
    };
  },
  methods: {
    submitData() {
      this.$emit(
      'add-contact', 
      this.enteredName, 
      this.enteredPhone, 
      this.enteredEmail
      );
    }
  },

};
</script>