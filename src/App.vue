<template>
  <div id="app">
    <win311-icon name="msdos" />
    <win311-window theme="cpanel" left="20%" top="0%" :mostrar="false" />
    <win311-window theme="games" left="25%" top="-8%" />
  </div>
</template>

<script>
import Win311Icon from "./components/Win311Icon.vue";
import Win311Window from "./components/Win311Window.vue";

export default {
  name: "App",
  components: {
    "win311-window": Win311Window,
    "win311-icon": Win311Icon
  }
};
</script>

<style>
body {
  background-color: rgb(51, 192, 178);
}
#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  margin-top: 60px;
}
</style>
