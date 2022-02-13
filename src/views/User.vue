<template>
  <div>
    <h1>Hello, {{ user }}</h1>
    <router-link to="/invoices">My invoices</router-link>
    <button @click="logOut" class="log-out">Log out</button>
  </div>
</template>

<script>
import store from "@/store";

export default {
  name: "User",
  data() {
    return {
      user: store.user,
    };
  },
  methods: {
    logOut() {
      store.user = null;
      this.$router.push("/");
    },
  },
};
</script>

<style scoped></style>
