<template>
  <div class="home">
    <h2>
      {{ appTitle }}
    </h2>

    <h3>{{ counterData.counterTitle }}</h3>
    <div>
      <button @click="decreaseCounter" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1)" class="btn">+</button>
      <button @click="increaseCounter(2)" class="btn">++</button>
    </div>

    <p>This counter is {{ oddOrEven }}.</p>

    <div class="edit">
      <h4>Edit Counter title:</h4>
      <input v-model="counterData.counterTitle" type="text" v-autofocus />
    </div>
  </div>
</template>

<script lang="ts" setup>
import {
  ref,
  reactive,
  computed,
  watch,
  onBeforeMount,
  onMounted,
  onBeforeUnmount,
  onUnmounted,
} from "vue";

import { vAutofocus } from "@/directives/vAutofocus";

const appTitle = "My Counter App";

const counterData = reactive({
  count: 0,
  counterTitle: "Day Counter",
});

onBeforeMount(() => {
  console.log("on Before Mount is fired");
});

//Executes when our component is loaded in to the browser
onMounted(() => {
  console.log("on Mounted is fired");
});

onBeforeUnmount(() => {
  console.log("On Before Unmount is fired");
});

//Executes when our component is unloaded in to the browser
onUnmounted(() => {
  console.log("On Unmounted is fired");
});

//watcher
watch(
  () => counterData.count,
  (mvalue, oldvalue) => {
    console.log("new Value: " + mvalue, "old Value: " + oldvalue);
  }
);

const oddOrEven = computed(() => {
  if (counterData.count % 2 === 0) return "Even";
  return "Odd";
});

const increaseCounter = (count: number) => {
  //counter.value++;
  counterData.count += count;
};
const decreaseCounter = () => {
  //if (counter.value > 0) counter.value--;
  counterData.count--;
};
</script>

<style>
.home {
  text-align: center;
  padding: 20px;
}

.btn,
.counter {
  font-size: 40px;
  margin: 20px;
}

.edit {
  margin-top: 50px;
}
</style>
