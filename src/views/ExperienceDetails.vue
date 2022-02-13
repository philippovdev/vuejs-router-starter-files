<template>
  <section>
    <h2>{{ experience.name }}</h2>
    <div class="experience-details">
      <img
        :src="require(`@/assets/${experience.image}`)"
        :alt="experience.name"
      />
      <p>{{ experience.description }}</p>
    </div>
  </section>
</template>

<script>
import store from "@/store";

export default {
  name: "ExperiencesDetails",
  props: {
    slug: {
      type: String,
      required: true,
    },
    experienceSlug: {
      type: String,
      required: true,
    },
  },
  computed: {
    destination() {
      return store.destinations.find((d) => d.slug === this.slug);
    },
    experience() {
      return this.destination.experiences.find(
        (e) => e.slug === this.experienceSlug
      );
    },
  },
};
</script>

<style scoped>
section {
  height: auto;
  width: 100%;
  max-height: 400px;
}

.experience-details {
  display: flex;
  padding: 40px 0;
  justify-content: space-between;
}

p {
  margin: 0 40px;
  font-size: 20px;
  text-align: left;
}
</style>
