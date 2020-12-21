<template>
  <v-app>
    <v-main>
      <ButtonDisplay />
    </v-main>
  </v-app>
</template>

<script>
import ButtonDisplay from "./components/ButtonDisplay";

export default {
  name: "App",

  components: {
    ButtonDisplay,
  },

  data: () => ({}),
};
</script>
