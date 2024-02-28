<template>
  <main>
    <banner-content />
    <div class="container">
      <tabs-view />
      <grid-view />
      <pagination-view />
      <contact-view />
    </div>
  </main>
</template>

<script setup>
import BannerContent from "./BannerContent.vue";
import TabsView from "./TabsView.vue";
import GridView from "./GridView.vue";
import PaginationView from "./PaginationView.vue";
import ContactView from "./ContactView.vue";
</script>
