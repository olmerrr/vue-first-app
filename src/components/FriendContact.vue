<template>
  <li>
    <h2>{{ name }} {{ isFavorite ? "(Favorite)" : "" }}</h2>
    <button @click="toggleFavorite">Toggle Favorite</button>

    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide" : "Show" }}
    </button>
    <ul v-if="detailsAreVisible">
      <li>{{ phoneNumber }}</li>
      <li>{{ emailAdres }}</li>
    </ul>
    <button @click="deleteFriend">Delete</button>
  </li>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    phoneNumber:  {
      type: String,
      required: true
      },
    emailAdres: {
      type: String,
      required: true
    },
    isFavorite:  {
      type: Boolean,
      required: false,
      default: false,
    }
  },
  emits: ['toggle-favorite', 'delete'],
  // emits: {
  //   'toggle-favorite': function(id){
  //     if (id) {
  //       return true;       
  //     } else {
  //       console.warn('Id is missing!');
  //       return false;
  //     }
  //   }
  //   },

  data() {
    return {
      detailsAreVisible: false,
    }
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit('toggle-favorite', this.id);
    },
    deleteFriend() {
      this.$emit('delete',this.id);
    },

  }
};
</script>