<template>
  <li>
    <h2>{{ name }} {{ friendIsFavorite === "1" ? "(Favorite)" : "" }}</h2>
    <button @click="toggleFavorite">Toggle Favorite</button>

    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide" : "Show" }}
    </button>
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
    'emailAdres',
    'isFavorite'
  ],
  data() {
    return {
      detailsAreVisible: false,
      friendIsFavorite: this.isFavorite,
      friend: {
        id: "manuel",
        name: "Manuel",
        phone: "011 44 11 23",
        email: "manu@ukr.net",
      },
    }
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      if(this.friendIsFavorite === '1'){
        this.friendIsFavorite = '0';
      }else {
        this.friendIsFavorite = '1';
      }
    }
  }
};
</script>