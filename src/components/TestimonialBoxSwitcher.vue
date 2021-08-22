<template>
  <div
    class="bg-blue-100 w-full font-sans h-full flex justify-center items-center"
  >
    <div class="py-10 px-14 rounded bg-blue-500" style="width: 800px">
      <div
        class="bg-white rounded-full h-1"
        style="transition: 0.1s linear"
        :style="`width: ${prograssLen}%`"
      ></div>
      <div class="mt-5 text-lg font-light text-white leading-7">
        This guy is a hard worker. Communication was also very good with him and
        he was very responsive all the time, something not easy to find in many
        freelancers. We'll definitely repeat with him.
      </div>
      <div class="mt-5 flex justify-center text-white items-center">
        <div class="w-52 h-24 grid grid-cols-2 grid-rows-2 gap-x-2">
          <div class="col-span-1 row-span-2">
            <div class="h-24 w-24 rounded-full bg-yellow-300"></div>
          </div>
          <div class="col-span-1 row-span-1 flex items-center font-medium">
            Name
          </div>
          <div class="col-span-1 row-span-1 flex items-center font-light">
            Name
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const prograssLen = ref(0);
    setInterval(() => {
      if (prograssLen.value < 100) prograssLen.value++;
      else prograssLen.value = 0;
    }, 100);
    return {
      prograssLen,
    };
  },
});
</script>

<style scoped>
</style>