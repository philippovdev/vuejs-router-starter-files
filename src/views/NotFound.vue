<template>
  <div>
    <h1>Not found</h1>
    <p>
      Oops! We didn't find this page. Try going to
      <router-link :to="{ name: 'Home' }">Home</router-link>
    </p>
  </div>
</template>

<script>
export default {
  name: "NotFound",
};
</script>

<style scoped></style>
