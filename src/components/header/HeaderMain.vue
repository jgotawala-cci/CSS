<template>
  <section class="header-main">
    <img src="../../styles/images/logo.png" width="152" height="48" />
    <nav>
      <a href="#">About</a>
      <a href="#">Services</a>
      <a href="#">Pricing</a>
      <a href="#">Blog</a>
    </nav>
    <div class="button-wrapper" @click="onShowOverlay">
      <button>Contact</button>
      <img src="../../styles/images/bars.svg" height="19" width="21" />
    </div>
    <header-overlay
      :overlayStyle="overlayStyle"
      :onCloseOverlay="onCloseOverlay"
      :visible="isVisible"
    />
  </section>
</template>

<script setup lang="ts">
import HeaderOverlay from "./HeaderOverlay.vue";

import { onBeforeUnmount, onMounted, ref, watch } from "vue";

const isMobile = ref(window.innerWidth <= 768); // Adjust the threshold as needed
const overlayStyle = ref({ right: "-90%" });
const isVisible = ref(false);

const handleResize = () => {
  isMobile.value = window.innerWidth <= 768; // Adjust the threshold as needed
};

const onShowOverlay = () => {
  if (isMobile.value) {
    overlayStyle.value = { right: "0%" };
    document.body.classList.add("no-scroll");
    isVisible.value = true;
  }
};

const onCloseOverlay = () => {
  overlayStyle.value = { right: "-90%" };
  document.body.classList.remove("no-scroll");
  isVisible.value = false;
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", handleResize);
});

watch(isMobile, () => {
  if (overlayStyle.value.right === "0%") {
    onCloseOverlay();
  }
});
</script>
