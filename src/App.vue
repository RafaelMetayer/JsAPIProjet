<template>
  <v-app id="inspire">
    <div>
      <v-toolbar>
        <v-toolbar-title>LOL ESport</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-toolbar-items>
          <v-btn text to="/">Home</v-btn>
          <v-btn text to="/tournois">Les tournois</v-btn>
          <v-btn text to="/equipes">Les equipes</v-btn>
          <v-btn text to="/champions">Les champions</v-btn>
          <v-btn text to="/items">Les items</v-btn>
          <v-btn text to="/about">A propos</v-btn>
        </v-toolbar-items>
      </v-toolbar>
    </div>
    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
  export default {
    name: "App",
    data() {
      return {
        drawer: false // Hide mobile side menu by default
      };
    }
  };
</script>