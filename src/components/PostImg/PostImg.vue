<template>
  <div class="post-img">
    <img :src="thumUrl" :alt="title" />
    <a :href="url" target="_blank">{{ title }}</a>
  </div>
</template>
<script>
export default {
  name: "PostImg",
  props: { title: String, url: String, thumUrl: String },
};
</script>

<style scoped>
.post-img {
  width: 100px;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}

a {
  text-decoration: none;
  position: absolute;
  left: 5px;
  bottom: 10px;
  color: rgb(3, 111, 111);
  font-size: 16px;
}
</style>
