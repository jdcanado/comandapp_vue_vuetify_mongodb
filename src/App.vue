<template>
  <div id="app">
    <v-app id="inspire" dark>
      <v-navigation-drawer clipped fixed v-model="drawer" app>
        <v-list dense>
          <v-list-tile @click="pagina = 'cadastroProduto';">
            <v-list-tile-action>
              <v-icon>dashboard</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>Cadastrar Produto</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-list-tile @click="pagina = 'Home';">
            <v-list-tile-action> <v-icon>settings</v-icon> </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>Home</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
      <v-toolbar app fixed clipped-left>
        <v-toolbar-side-icon
          @click.stop="drawer = !drawer;"
        ></v-toolbar-side-icon>
        <v-toolbar-title>ComandApp OTech Development</v-toolbar-title>
      </v-toolbar>
      <v-content>
        <v-container fluid fill-height>
          <v-layout justify-center align-center>
            <v-flex v-if="pagina === 'Home'" shrink>
              <img width="25%" src="./assets/logo.png" /> <HelloWorld />
            </v-flex>
            <v-flex v-else-if="pagina === 'cadastroProduto'" shrink>
              <CadastroProduto />
            </v-flex>
          </v-layout>
        </v-container>
      </v-content>
      <v-footer app fixed> <span>&copy; 2019</span> </v-footer>
    </v-app>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import CadastroProduto from "./components/CadastroProduto";

export default {
  name: "App",
  components: {
    HelloWorld,
    CadastroProduto
  },
  data: () => ({
    drawer: false,
    pagina: "Home"
  }),
  props: {
    source: String
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
