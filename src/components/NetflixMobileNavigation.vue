<template>
  <div class="w-full h-full bg-yellow-100">
    <div class=" z-10 absolute top-5 left-5 bg-white">
      <button @click="show = !show" class="bg-white p-3">click me</button>
    </div>
    <div
      class="h-full fixed top-0 bg-black"
      style="width: 30%; transition-delay: 100ms; transition: 100ms;"
      :style="'transform: translateX(' + (!show ? '-100%' : '0%') + ')'"
    ></div>
    <div
      class="h-full fixed top-0 bg-red-500"
      style="width: 28%; transition-delay: 500ms;  transition: 500ms;"
      :style="'transform: translateX(' + (!show ? '-100%' : '0%') + ')'"
    ></div>
    <div
      class="h-full fixed top-0 bg-white"
      style="width: 26%; transition-delay: 1000ms; transition: 1000ms;"
      :style="'transform: translateX(' + (!show ? '-100%' : '0%') + ')'"
    ></div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const show = ref(false);
    return {
      show,
    };
  },
});
</script>

<style scoped>
@keyframes slidOut {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0%);
  }
}
.ani {
  transition: .3s cubic-bezier(0.39, 0.575, 0.565, 1);
  animation: slidOut 1;
}
</style>