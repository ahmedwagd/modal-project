<template>
  <div class="post">
    <h5 class="post__title">{{ title }}</h5>
    <p class="post__body">{{ body }}</p>
  </div>
</template>
<script>
export default {
  name: "Post",
  props: { title: String, body: String },
};
</script>

<style scoped>
.post {
  width: 600px;
  background: darkcyan;
  padding: 20px 5px;
  margin: 20px 0;
  text-align: center;
}
.post__title {
  color: rgb(5, 60, 60);
  font-size: 22px;
}
.post__body {
  color: rgb(3, 111, 111);
  font-size: 20px;
}
</style>
