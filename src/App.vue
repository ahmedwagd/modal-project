<template>
  <!-- <Navbar /> -->
  <button @click="toggleMo">Click</button>
  <span @click="colS">s</span>
  <!-- <Wellcome age="10" /> -->
  <div v-if="isShow">
    <Model theme="sale" @sayOk="colS">
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">Sign in</a>
      </template>
      <h1>Ninja Givaway</h1>
      <p>lets fo ghok maj andkj kshfda</p>
    </Model>
  </div>
  <div class="posts__container">
    s
    <teleport to=".modals">
      <Model theme="sale" @sayOk="colS">
        <template v-slot:links> </template>
        <h1>Ninja Givaway</h1>
        <p>lets fo ghok maj andkj kshfda</p>
      </Model>
    </teleport>
    <!-- <Post
      v-for="post in posts"
      :key="post.id"
      :title="post.title"
      :body="post.body"
    /> -->
    <!-- <PostImg
      v-for="photo in photos"
      :key="photo.id"
      :title="photo.title"
      :url="photo.url"
      :thumUrl="photo.thumbnailUrl"
    /> -->
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Wellcome from "./components/Wellcome.vue";
import Model from "./components/Modal/Model.vue";
import Post from "./components/Post/Post.vue";
import PostImg from "./components/PostImg/PostImg.vue";

import "./global.css";

import axios from "axios";
import faker from "faker";

export default {
  name: "App",
  components: {
    Wellcome,
    Navbar,
    Model,
    Post,
    PostImg,
  },
  data() {
    return {
      header: "ok",
      content: "wellcome",
      posts: [],
      photos: [],
      rand: faker.name.findName(),
      img: faker.image.avatar(),
      imgAlt: faker.image.animals(),
      isShow: true,
    };
  },
  methods: {
    toggleMo() {
      this.isShow = !this.isShow;
    },
    colS() {
      console.log("Ok!!");
    },
  },
  mounted() {
    axios
      .get("https://jsonplaceholder.typicode.com/photos")
      .then(({ data }) => {
        this.photos = data.slice(0, 10);
      })
      .catch((error) => {
        this.errorMessage = error.message;
        console.error("There was an error!", error);
      });
    console.log(this.img);
  },
};
</script>
