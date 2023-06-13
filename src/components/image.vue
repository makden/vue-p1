<template>
  <div id="images">
    <img v-bind:src="srcpath" v-bind:alt="srcpath" v-bind:title="titletext" />
    <br /><b>{{ name }}</b>
  </div>
</template>

<script>
export default {
  name: 'images',
  props: {
    srcpath: String,
    titletext: String,
    name: String,
  },
  data() {
    return {
      imgDef: this.srcpath,
    };
  },
};
</script>

<style scoped>
img {
  border: solid 1px #888;
  width: auto;
  height: 50px;
}

#images {
  border-radius: 5px;
  background-color: #ddd;
  width: 100%;
}
</style>
