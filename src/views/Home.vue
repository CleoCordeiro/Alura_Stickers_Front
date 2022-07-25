<template>

  <v-app :style="{ background: $vuetify.theme.themes.dark.background }">
    <v-container>

      <MakerSticker />
    </v-container>
    <v-container>
      <h1 class="white--text">Exemplos de Stickers Gerados</h1>
      <p class="grey--text">
        Com Grandes Poderes Vêm Grandes Responsabilidades
      </p>


      <v-divider color="grey"></v-divider>
      <v-toolbar flat color="rgba(0,0,0,0)">
        <v-spacer></v-spacer>
      </v-toolbar>
      <Stickers />

    </v-container>
    <Footer />
  </v-app>
</template>

<script>
import Stickers from "../components/Stickers.vue";
import MakerSticker from "../components/MakerSticker.vue";
import Footer from "../components/Footer.vue";

export default {
  name: "Home",
  emitis: ['toogleDrawer'],
  components: {
    Stickers,
    MakerSticker,
    Footer
  },
  methods: {
    ChangeDrawer() {
      this.drawer = !this.drawer;
    }
  },
};

</script>
<style scoped>
</style>
