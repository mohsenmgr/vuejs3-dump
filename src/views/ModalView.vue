<template>
  <h1>Modal View</h1>
  <button @click="changeVisibility">Show Post</button>

  <Teleport to=".modals-container">
    <div v-show="showPost" class="modal">
      <h1>This is a modal</h1>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Magni aut cum corrupti
        nihil sit, accusamus pariatur obcaecati, ipsa distinctio non dignissimos
        consequuntur ex. Reiciendis obcaecati, dignissimos soluta officiis excepturi
        cupiditate?
      </p>
      <button @click="changeVisibility" v-show="showPost">Hide Post</button>
    </div>
  </Teleport>
</template>

<script lang="ts" setup>
import { ref } from "vue";

const showPost = ref(false);

const changeVisibility = () => {
  showPost.value = !showPost.value;
};
</script>

<style>
.modal {
  margin: 20px;
  background-color: grey;
  padding: 10px;
  position: absolute;
  left: 0;
  top: 0;
  width: 90%;
  height: 90%;
  z-index: 1;
}
</style>
