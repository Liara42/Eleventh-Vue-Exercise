<template>
  <li>
    <h2>{{ name }} {{ friendIsFavorite ? "(Favorite)" : "" }}</h2>
    <button @click="toggleFavorite">Toggle Favorite</button>
    <button @click="toggleDetails">
      {{ visibleDetails ? "Hide" : "Show" }} Details
    </button>
    <ul v-if="visibleDetails">
      <li>
        <strong>Phone: </strong>
        {{ phoneNumber }}
      </li>
      <li>
        <strong>Email: </strong>
        {{ emailAddress }}
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  props: ["name", "phoneNumber", "emailAddress", "isFavorite"],
  data() {
    return {
      visibleDetails: false,
      contact: {
        id: "manuel",
        name: "Manuel Lorenz",
        phone: "0123 45678 90",
        email: "manuel@localhost.com",
      },
      friendIsFavorite: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.visibleDetails = !this.visibleDetails;
    },
    toggleFavorite() {
      this.friendIsFavorite = !this.friendIsFavorite;
    },
  },
};
</script>