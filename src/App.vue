<template>
  <Header :hdr="title" />
  <Tabs />
</template>

<script>
import Header from "./components/Header.vue";
import Tabs from "./components/Tabs.vue";

export default {
  name: "App",
  components: {
    Tabs,
    Header,
  },
  data() {
    return {
      title: "Vue basics",
    };
  },

};
</script>

<style >
@import url("https://fonts.googleapis.com/css2?family=Lato:wght@300&display=swap");
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
 
}
#app {
  font-family: "Lato", Helvetica, Arial, sans-serif;

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>