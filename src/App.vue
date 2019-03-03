<template>
  <v-app>
    <v-toolbar>
      <v-toolbar-title class="headline">로얄신용평가</v-toolbar-title>
      <v-spacer></v-spacer>
      <a href="#">
        <i class="material-icons ico_gnb">menu</i>
      </a>
    </v-toolbar>

    <v-content>
      <HelloWorld/>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  components: {
    HelloWorld
  },
  data() {
    return {
      //
    };
  }
};
</script>

<style>
.ico_gnb {font-size:33px; line-height:43px}
</style>

