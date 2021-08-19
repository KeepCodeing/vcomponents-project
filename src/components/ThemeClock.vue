<template>
  <div class="bg-white h-full w-full flex justify-center items-center">
    <div class="relative h-2/5 w-1/5 transform rotate-90">
      <div
        class="
          bg-black
          border-2
          absolute
          left-1/2
          top-1/2
          transform
          -translate-x-1/2 -translate-y-1/2
          border-red-500
          h-1
          w-1
          z-10
          rounded-full
          p-1
        "
      ></div>
      <div
        class="absolute left-1/2 top-1/2 bg-red-500 h-24 w-0.5"
        style="transform: translate(-50%); transform-origin: top center"
        :style="{ transform: 'rotate(' + second * 6 + 'deg)' }"
      ></div>
      <div
        class="absolute left-1/2 top-1/2 bg-yellow-500 h-16 w-0.5"
        style="transform: translate(-50%); transform-origin: top center"
        :style="{ transform: 'rotate(' + minute * 6 + 'deg)' }"
      ></div>
      <div
        class="absolute left-1/2 top-1/2 bg-black h-16 w-0.5"
        style="transform: translate(-50%); transform-origin: top center"
        :style="{ transform: 'rotate(' + hour * 15 + 'deg)' }"
      ></div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, watch } from "vue";

export default defineComponent({
  setup() {
    const d = new Date();
    const second = ref(d.getSeconds());
    const minute = ref(d.getMinutes());
    const hour = ref(d.getHours());

    const timer = setInterval(() => {
      const d = new Date();
      second.value = d.getSeconds();
      minute.value = d.getMinutes();
      hour.value = d.getHours();
    }, 500);

    return {
      second,
      minute,
      hour,
    };
  },
});
</script>

<style scoped>
</style>