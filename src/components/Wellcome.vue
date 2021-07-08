<template>
  <div class="ok">
    <h1>Wellcome</h1>
    <p>{{ age }}</p>
  </div>
</template>
<script>
export default {
  name: "Wellcome",
  props: {
    age: String,
  },
};
</script>
<style scoped>
.ok {
  color: tomato;
}
</style>
