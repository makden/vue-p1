<template>
  <header>
    <div class="hello">
      <h1>{{ nameBox }}</h1>
    </div>
  </header>
</template>

<script>
export default {
  name: 'headerBox',
  props: {
    nameBox: String,
  },
};
</script>

<style scoped>
header {
  background-color: #f3f3f3;
}
</style>
