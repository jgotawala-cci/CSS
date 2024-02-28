<template>
  <section class="banner-wrapper">
    <h1>Portfolio</h1>
    <p>
      Agency provides a full service range including technical skills,
      design,<span v-if="!isMobile"><br /></span> business understanding.
    </p>
  </section>
</template>

<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from "vue";

const isMobile = ref(window.innerWidth <= 660); // Adjust the threshold as needed

const handleResize = () => {
  isMobile.value = window.innerWidth <= 660; // Adjust the threshold as needed
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", handleResize);
});
</script>
