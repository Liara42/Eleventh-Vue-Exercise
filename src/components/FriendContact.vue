<template>
  <li>
    <h2>{{ contact.name }}</h2>
    <button @click="toggleDetails">
      {{ visibleDetails ? "Hide" : "Show" }} Details
    </button>
    <ul v-if="visibleDetails">
      <li>
        <strong>Phone: </strong>
        {{ contact.phone }}
      </li>
      <li>
        <strong>Email: </strong>
        {{ contact.email }}
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  data() {
    return {
      visibleDetails: false,
      contact: {
        id: "manuel",
        name: "Manuel Lorenz",
        phone: "0123 45678 90",
        email: "manuel@localhost.com",
      },
    };
  },
  methods: {
    toggleDetails() {
      this.visibleDetails = !this.visibleDetails;
    },
  },
};
</script>