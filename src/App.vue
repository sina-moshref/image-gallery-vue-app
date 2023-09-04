<template>
  <v-app>
    <SideBar @image-mode="updateMode" />
    <v-main>
      <MainContent :image-color="mode" />
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from "vue";
import SideBar from "./layouts/SideBar.vue";
import MainContent from "./layouts/MainContent.vue";

const mode = ref("");

const updateMode = (newMode) => {
  if (newMode) {
    mode.value = newMode;
  } else {
    mode.value = newMode;
  }
};
</script>
