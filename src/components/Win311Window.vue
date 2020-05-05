<template>
  <div class="window">
    <div class="contenido">
      <div class="titulo">
        {{ title }}
        <div class="button" id="dch">&#9660;</div>
        <div class="button" id="izq">&#8212;</div>
      </div>
      <div class="menu">Settings Help</div>
      <div class="container">
        <win311-icon v-for="(name, index) in this.icons" :name="icons[index]" :key="index"></win311-icon>
      </div>
    </div>
    <div class="pie">Select app to open...</div>
  </div>
</template>

<script>
import Win311Icon from "../components/Win311Icon";
import json from "../assets/windows.json";

export default {
  name: "Win311Window",
  components: {
    "win311-icon": Win311Icon
  },
  props: {
    theme: {
      type: String,
      default: "normal",
      required: true
    }
  },
  data() {
    return {
      title: "",
      icons: []
    };
  },
  methods: {
    getVariables() {
      var ind = this.theme;
      this.title = json[ind].title;
      this.icons = json[ind].icons;
    }
  },
  beforeMount() {
    this.getVariables();
  }
};
</script>

<style scoped>
.window {
  background-color: lightgray;
  padding: 2px 8px 4px 8px;
  width: 700px;
  height: 500px;
  margin-left: auto;
  margin-right: auto;
  border-bottom: solid 1px black;
}

.contenido {
  background-color: white;
  width: 100%;
  height: 460px;
}

.titulo {
  background-color: rgb(20, 20, 167);
  margin-left: auto;
  margin-right: auto;
  margin-top: 0.5%;
  color: white;
  font-size: 20px;
  line-height: 30px;
  width: 700px;
  height: 30px;
  border-bottom: solid 1px #000;
}

.button {
  background: lightgray;
  color: rgb(39, 39, 39);
  display: inline-block;
  margin: 0px;
  width: 30px;
  height: 23px;
  font-size: 20px;
  border: outset 4px;
  line-height: 20px;
}
#dch {
  float: right;
}
#izq {
  float: left;
}

.menu {
  width: 100%;
  border-bottom: solid 2px lightgray;
  padding: 10px 4px 5px;
  text-align: left;
  word-spacing: 10pt;
}

.pie {
  text-align: left;
  padding: 10px;
}

.container {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  grid-gap: 10px 10px;
  padding: 5px;
  font-size: 12px;
  color: rgb(39, 39, 39);
}
</style>
