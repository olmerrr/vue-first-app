<template>
  <li>
    <h2>{{ name }}</h2>
    <button @click="toggleDetails">{{detailsAreVisible ? 'Hide' : 'Show'}}</button>
    <ul v-if="detailsAreVisible">
      <li>{{ phoneNumber }}</li>
      <li>{{ emailAdres }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  props: [
    'name',
    'phoneNumber',
    'emailAdres'
  ],
  data() {
    return {
      detailsAreVisible: false,
      friend: {
        id: "manuel",
        name: "Manuel",
        phone: "011 44 11 23",
        email: "manu@ukr.net",
      },
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    }
  }
};
</script>