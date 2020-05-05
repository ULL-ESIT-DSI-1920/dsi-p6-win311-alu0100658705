<template>
  <div class="icon">
    <img :src="require(`@/assets/icons/${image}`)" />
    <h5>{{name}}</h5>
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
      image: this.name + ".png"
    };
  }
};
</script>

<style>
.icon {
  display: absolute;
  margin-top: 2px;
  margin-left: 0px;
}
</style>
