<template>
  <section>
    <h2>My frinds</h2>
    <ul>
      <friend-contact></friend-contact>
      <friend-contact></friend-contact>
    </ul>
  </section>
</template>



<script>
export default {
  data() {
    return {
      friends: [
        {
          id: "manuel",
          name: "Manuel",
          phone: "011 44 11 23",
          email: "manu@ukr.net",
        },

        {
          id: "lama",
          name: "Lama",
          phone: "012 40 61 30",
          email: "lama12@ukr.net",
        },
      ],
    };
  },
};
</script>
