<template>
  <nav>
    <a href="#">Show All<sup>14</sup></a>
    <a href="#">Design<sup>6</sup></a>
    <a href="#">Branding<sup>4</sup></a>
    <a href="#">Illustration<sup>3</sup></a>
    <a href="#">Motion<sup>1</sup></a>
  </nav>

  <div class="dropdown" :class="{ active: showDropdown }">
    <section class="dropdown-view" @click="toggelDropdown">
      <label>{{ selected }}</label>
      <img :src="dropDowndownImg" class="triangle" height="16" width="20" />
    </section>
    <div class="dropdown-content">
      <ul>
        <li v-for="tab in tabs" :key="tab" @click="selectTab(tab)">
          <a :class="{ selected: selected === tab }">{{ tab }}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const showDropdown = ref(false);
const dropDowndownImg = ref(require("../../styles/images/down.svg"));
const selected = ref("Show All");

const tabs = ["Show All", "Design", "Branding", "Illustration", "Motion"];

const toggelDropdown = () => {
  showDropdown.value = !showDropdown.value;
  dropDowndownImg.value = showDropdown.value
    ? require("../../styles/images/up.svg")
    : require("../../styles/images/down.svg");
};

const selectTab = (tabName: string) => {
  selected.value = tabName;
  toggelDropdown();
};
</script>
