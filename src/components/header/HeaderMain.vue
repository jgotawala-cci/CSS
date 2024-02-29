<template>
  <section class="header-main">
    <img src="../../styles/images/logo.png" />
    <nav>
      <a href="#">About</a>
      <a href="#">Services</a>
      <a href="#">Pricing</a>
      <a href="#">Blog</a>
    </nav>
    <div class="button-wrapper" @click="onShowOverlay">
      <button>Contact</button>
      <img src="../../styles/images/bars.svg" />
    </div>
    <header-overlay
      :overlayStyle="overlayStyle"
      :onCloseOverlay="onCloseOverlay"
    />
  </section>
</template>

<script setup lang="ts">
import HeaderOverlay from "./HeaderOverlay.vue";

import { onBeforeUnmount, onMounted, ref } from "vue";

const isMobile = ref(window.innerWidth <= 768); // Adjust the threshold as needed
const overlayStyle = ref({ right: "-90%" });

const handleResize = () => {
  isMobile.value = window.innerWidth <= 768; // Adjust the threshold as needed
};

const onShowOverlay = () => {
  if (isMobile.value) {
    overlayStyle.value = { right: "0%" };
  }
};

const onCloseOverlay = () => {
  overlayStyle.value = { right: "-90%" };
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", handleResize);
});
</script>
