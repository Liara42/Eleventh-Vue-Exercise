<template>
  <li>
    <h2>{{ name }} {{ isFavorite ? "(Favorite)" : "" }}</h2>
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
  props: ["id", "name", "phoneNumber", "emailAddress", "isFavorite"],
  data() {
    return {
      visibleDetails: false,
    };
  },
  methods: {
    toggleDetails() {
      this.visibleDetails = !this.visibleDetails;
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.id);
    },
  },
};
</script>