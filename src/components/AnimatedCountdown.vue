<template>
  <div class="h-full w-ufll bg-white flex justify-center items-center">
    <div
      class="flex flex-col justify-center items-center h-24 w-24"
    >
      <div
        v-for="item in 1"
        :key="item"
        class="text-blue-400 text-3xl font-bold an"
      >
        {{ item }}
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const limit = ref(3);

    return {
      limit,
    };
  },
});
</script>

<style scoped>
@keyframes rotateIn {
  0% {
    transform: rotate(90deg) scale(1.05);
  }
  50% {
    transform: rotate(0deg) scale(1.15);
  }
  80% {
    transform: rotate(45deg) scale(1.55);
  }

  100% {
    transform: rotate(-90deg) scale(1.7);
  }
}
.an {
  animation: rotateIn 1s ease-in-out;
}
</style>