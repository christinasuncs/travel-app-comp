<template>
  <section>
    <h1>{{ experience.name }}</h1>
    <img :src="`/images/${experience.image}`" :alt="experience.name" />
    <p>{{ experience.description }}</p>
  </section>
</template>

<script>
import { ref, computed } from "vue";
import sourceData from "@/data.json";

export default {
  props: {
    id: { type: Number, required: true },
    experienceSlug: { type: String, required: true },
  },
  setup(props) {
    const destination = computed(() => {
      return sourceData.destinations.find(
        (destination) => destination.id === props.id
      );
    });

    const experience = computed(() => {
      if (destination.value) {
        return destination.value.experiences.find(
          (experience) => experience.slug === props.experienceSlug
        );
      }
      return null;
    });

    return { experience };
  },
};
</script>
