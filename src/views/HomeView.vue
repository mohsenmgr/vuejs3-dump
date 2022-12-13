<template>
  <div class="home">
    <h2>
      {{ appTitle }}
    </h2>

    <h3>{{ counterData.counterTitle }}</h3>
    <div>
      <button @click="decreaseCounter" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter" class="btn">+</button>
    </div>

    <div class="edit">
      <h4>Edit Counter title:</h4>
      <input v-model="counterData.counterTitle" type="text" />
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref, reactive } from "vue";

// const counter = ref(0),
//   counterTitle = ref("Day Counter");

const appTitle = "My Counter App";

const counterData = reactive({
  count: 0,
  counterTitle: "Day Counter",
});

const increaseCounter = () => {
  //counter.value++;
  counterData.count++;
};
const decreaseCounter = () => {
  //if (counter.value > 0) counter.value--;
  counterData.count--;
};
</script>

<!--
<script lang="ts">
export default {
  data() {
    return {
      counter: 0,
    };
  },
  methods: {
    increaseCounter: function () {
      this.counter++;
    },
    decreaseCounter: function () {
      if (this.counter > 0) this.counter--;
    },
  },
};
</script>
!-->

<!-- Old method Composition API
<script lang="ts">
import { ref } from "vue";
export default {
  setup() {
    const counter = ref(0);

    const increaseCounter = () => {
      counter.value++;
    };
    const decreaseCounter = () => {
      if (counter.value > 0) counter.value--;
    };

    return {
      counter,
      increaseCounter,
      decreaseCounter,
    };
  },
};
</script>
!-->

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
