<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline">
        <span class="font-weight-light">Ussy's portfolio</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        v-for="(next, i) in headerItems"
        :key="i"
        :href="next.href"
        class="my-2"
      >{{ next.text }}</v-btn>
    </v-toolbar>
    <v-content>
      <HelloWorld />
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
  data: () => ({
    headerItems: [
      {
        text: "Home",
        href: "#"
      },
      {
        text: "Skills",
        href: "#skills"
      },
      {
        text: "Career",
        href: "#career"
      },
      {
        text: "Activity",
        href: "#activity"
      }
    ]
  })
};
</script>