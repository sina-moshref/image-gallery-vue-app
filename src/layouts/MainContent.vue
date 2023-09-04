<template>
  <v-container>
    <v-row>
      <v-col v-for="n in 200" :key="n" cols="4" sm="3" md="2" lg="1">
        <v-card
          @click="
            copyToclipboardHandler(
              `https://picsum.photos/500/300?image=${n * 5 + 10}${imageColor}`
            )
          "
        >
          <v-img
            :src="`https://picsum.photos/500/300?image=${
              n * 5 + 10
            }${imageColor}`"
            :lazy-src="`https://picsum.photos/10/6?image=${
              n * 5 + 10
            }${imageColor}`"
            aspect-ratio="1"
            cover
          >
            <template v-slot:placeholder>
              <v-row class="fill-height ma-0" align="center" justify="center">
                <v-progress-circular
                  indeterminate
                  color="grey-lighten-5"
                ></v-progress-circular>
              </v-row> </template
          ></v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref, watch } from "vue";

const props = defineProps(["imageColor"]);
const colored = ref(props.imageColor ? props.imageColor : "");

const copyToclipboardHandler = (url) => {
  navigator.clipboard.writeText(url);
};
</script>
