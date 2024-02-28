<template>
  <section class="grid-container">
    <figure v-for="option in options" :key="option.id">
      <img :src="option.image" :alt="option.image" />
      <figcaption>
        <span>{{ option.type }}</span>
        <h2>
          {{ option.name }}
        </h2>
      </figcaption>
    </figure>
  </section>
</template>

<script setup lang="ts">
const options = [
  {
    id: 0,
    type: "Branding",
    name: "KeyBoard",
    image: require("../../styles/images/key-board.png"),
  },
  {
    id: 2,
    type: "Design",
    name: "SOFA",
    image: require("../../styles/images/sofa.png"),
  },
  {
    id: 3,
    type: "Illustration",
    name: "Work Media",
    image: require("../../styles/images/work-media.png"),
  },
  {
    id: 4,
    type: "Motion",
    name: "DDDone",
    image: require("../../styles/images/d-d-done.png"),
  },
  {
    id: 5,
    type: "Branding",
    name: "HandP",
    image: require("../../styles/images/hand-p.png"),
  },
];
</script>
