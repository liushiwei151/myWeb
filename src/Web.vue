<template>
  <div id="web">
    <head-bar></head-bar>
    <router-view />
  </div>
</template>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import headBar from "./components/web/headBar.vue";
@Component({
  components: {
    headBar
  }
})
export default class Web extends Vue {}
</script>
<style lang="less">
body {
  margin: 0;
  padding: 0;
  word-break: break-word;
}
#web {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
