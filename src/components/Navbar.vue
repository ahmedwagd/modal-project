<template>
  <header>
    <div><span>Logo</span></div>
    <nav>
      <span class="links">Home</span>
      <span class="links">About</span>
      <span class="links">Contact</span>
    </nav>
  </header>
</template>
<script>
export default {
  name: "Navbar",
};
</script>
<style scoped>
header {
  background: thistle;
  margin: 0 auto;
  padding: 10px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
div span {
  color: tomato;
  font-size: 24px;
}
nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
