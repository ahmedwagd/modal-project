<template>
  <div
    class="dark-bakground active"
    :class="{ sale: theme === 'sale' }"
    ref="close"
  >
    <div class="model">
      <span @click="handeClose">X</span>
      <div class="model-content">
        <slot></slot>
        <div class="actions">
          <slot name="links"></slot>
        </div>
        <button @click="$emit('sayOk')">Clos</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Model",
  props: ["theme"],
  emits: ["sayOk"],
  methods: {
    handeClose() {
      this.$refs.close.classList.remove("active");
    },
    handelS() {
      this.$emit("sayOk");
    },
  },
};
</script>

<style scoped>
/* .dark-bakground {
  display: none;
} */
.dark-bakground.active {
  position: fixed;
  width: 100%;
  height: 100%;
  background: #80808070;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 99;
}
.model {
  position: relative;
  background: white;
  padding: 50px;
  width: 400px;
  height: 400px;
}
.model span {
  width: 10px;
  height: 10px;
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: 20px;
  color: black;
  cursor: pointer;
}
.model span:hover {
  color: rgba(0, 0, 0, 0.59);
}
h1 {
  color: teal;
}
p {
  padding: 10px 20px;
  color: tomato;
}
.dark-bakground.sale .model div h1 {
  color: blue;
}
.actions {
  text-align: center;
  margin: 30px 0 10px;
}
.actions a {
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 4px;
  margin: 10px;
  text-decoration: none;
}
</style>
