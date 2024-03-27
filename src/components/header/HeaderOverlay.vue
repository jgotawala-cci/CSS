<template>
  <div class="overlay-wrapper" :class="{ show: visible }">
    <aside class="overlay" :style="props.overlayStyle">
      <a
        href="javascript:void(0)"
        class="close-btn"
        @click="props.onCloseOverlay"
      >
        <img src="../../styles/images/x-mark.svg" width="30" height="30" />
      </a>
      <nav>
        <a href="#" @click="props.onCloseOverlay">About</a>
        <a href="#" @click="props.onCloseOverlay">Services</a>
        <a href="#" @click="props.onCloseOverlay">Pricing</a>
        <a href="#" @click="props.onCloseOverlay">Blog</a>
        <a href="#" @click="props.onCloseOverlay">Contact</a>
      </nav>
    </aside>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps(["overlayStyle", "onCloseOverlay", "visible"]);
</script>
