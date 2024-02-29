<template>
  <section class="footer-bottom-wrapper">
    <span>
      Copyright &copy; 2022 Laaqiq.
      <span v-if="isMobile"><br /></span>
      All Rights Reserved.
    </span>
    <nav>
      <a href="#">Terms of Use</a>
      <a href="#" class="no-margin">Privacy Policy</a>
    </nav>
  </section>
</template>

<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from "vue";

const isMobile = ref(window.innerWidth <= 768); // Adjust the threshold as needed

const handleResize = () => {
  isMobile.value = window.innerWidth <= 768; // Adjust the threshold as needed
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", handleResize);
});
</script>
