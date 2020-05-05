<template>
  <div v-on:click="resaltar" v-on:dblclick="mensaje" class="icon">
    <img :src="require(`@/assets/icons/${image}`)" />
    <h5 class="texto" :style="{background: color}">{{name}}</h5>
  </div>
</template>

<script>
export default {
  name: "Win311Icon",
  props: {
    name: String
  },
  data() {
    return {
      image: this.name + ".png",
      color: "none",
      cont: 0
    };
  },
  methods: {
    mensaje: function(event) {
      alert("Has pulsado " + this.name);
    },
    resaltar: function(event) {
      if (this.cont === 0) {
        this.color = "rgb(141, 141, 235)";
        this.cont = 1;
        return {
          "--color": this.color
        };
      } else {
        this.color = "none";
        this.cont = 0;
        return {
          "--color": this.color
        };
      }
    }
  }
};
</script>

<style>
.icon {
  display: absolute;
  margin-top: 2px;
  margin-left: 0px;
  font-size: 12px;
  color: rgb(39, 39, 39);
}

.texto {
  background-color: var(--color);
}
</style>
