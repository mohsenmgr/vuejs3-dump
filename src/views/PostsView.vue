<template>
  <div class="posts">
    <h1>Posts</h1>

    <ul>
      <li v-for="post in posts" :key="post.id">
        <RouterLink :to="`/postDetail/${post.id}`">{{ post.title }}</RouterLink>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";

const posts = ref([
  {
    id: "id1",
    title: "post1",
  },
  {
    id: "id2",
    title: "post2",
  },
  {
    id: "id3",
    title: "post3",
  },
]);
</script>

<style scoped>
ul {
  margin-bottom: 13px;
}
li {
  padding-left: 10px;
}
</style>
