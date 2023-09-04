<template>
  <v-navigation-drawer expand-on-hover rail>
    <v-list>
      <v-list-item
        id="hero-img"
        :prepend-avatar="imgUrl"
        title="Sina Moshref"
        subtitle="sina.moshref@gmailcom"
        cover
      ></v-list-item>
    </v-list>

    <v-divider></v-divider>

    <v-list density="compact" nav>
      <v-list-item
        prepend-icon="mdi-image"
        title="Color Gallery"
        value="color"
        @click="updateMode('')"
      ></v-list-item>
      <v-list-item
        prepend-icon="mdi-dialpad"
        title="Grayspace Gallery"
        value="grey"
        @click="updateMode('&grayscale')"
      ></v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script setup>
import imgUrl from "../assets/my_pic.jpg";
const emit = defineEmits(["imageMode"]);
// document.getElementById('hero-img').src = imgUrl

const updateMode = (val) => {
  emit("imageMode", val);
};
</script>
