<template>
  <HeaderApp />
  <ContentApp />
  <FooterApp />
</template> 

<script>

import HeaderApp from "./components/HeaderApp.vue";
import ContentApp from "./components/ContentApp.vue";
import FooterApp from "./components/FooterApp.vue";

export default {
  name: 'App',
  components: {
    HeaderApp,
    ContentApp,
    FooterApp
  }
}
</script>

<style>
body {
  background: rgb(32, 33, 36);
}
</style>
