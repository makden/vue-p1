<template>
  <div id="images">
    <img v-bind:src="srcpath" v-bind:title="titletext" />
  </div>
</template>

<script>
export default {
  name: 'images',
  props: {
    srcpath: String,
    titletext: String,
  },
  emits: ['update:srcpath'],
};
</script>

<style scoped>
img {
  border: solid 1px #888;
  width: 100%;
}

#images {
  border-radius: 5px;
  background-color: #ddd;
  width: 100%;
}
</style>
