<template>
  <div class="post-detail">
    <h1>Post Detail</h1>
    <p>Display the content of the page with the ID of {{ $route.params.id }}</p>
    <div><button @click="showPostId">Show Post ID</button></div>
    <div><button @click="goHomeYou">GO Home in 3 Seconds</button></div>
    <div><button @click="goToFirst">GO To First post</button></div>

    <p><RouterLink to="/posts">&lt; Back</RouterLink></p>
  </div>
</template>

<script lang="ts" setup>
import { useRoute, useRouter } from "vue-router";

// we can access useRoute composable using the route constant
const route = useRoute();

const showPostId = () => {
  alert(`The id of this post is ${route.params.id}.`);
};

const router = useRouter();
const goHomeYou = () => {
  setTimeout(() => {
    router.push({ name: "home" });
  }, 3000);
};

const goToFirst = () => {
  router.push({
    name: "postDetail",
    params: {
      id: "id1",
    },
  });
};
</script>
