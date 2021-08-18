<template>
  <div class="h-full w-full bg-blue-400 flex justify-center items-center">
    <div class="h-full">
      <div class="text-center mt-5">
        <h1 class="text-3xl font-bold text-white">Drink Water</h1>
        <p class="text-lg text-white">Goal: 2 Liters</p>
      </div>
      <div
        class="
          border-4
          mt-5
          rounded-bl-3xl rounded-br-3xl
          overflow-hidden
          border-blue-600
          h-2/3
        "
      >
        <div
          class="
            bg-white
            flex
            justify-center
            text-blue-700 text-lg
            items-center
            w-full
            water-height
            text-center
            overflow-hidden
          "
          :style="{ height: 100 - usedCon + '%' }"
        >
          <div>
            <p class="font-bold">{{ 2 - 2 * usedCon / 100 }}L</p>
            <p class="font-thin">Remained</p>
          </div>
        </div>
        <div
          class="
            bg-blue-500
            flex
            items-center
            justify-center
            text-white
            w-full
            water-height
          "
          :style="{ height: usedCon + '%' }"
        >
          <p class="font-bold text-2xl">{{ usedCon }}%</p>
        </div>
      </div>
      <div class="mt-2 grid grid-cols-4">
        <div
          class="
            border-2
            rounded-bl-3xl rounded-br-3xl
            border-blue-600
            h-14
            w-10
            font-light
            text-sm text-center
            mt-2
            bg-white
            text-blue-500
            cursor-pointer
          "
          :class="{ 'bg-blue-200': item <= curIdx }"
          v-for="item in 8"
          :key="item"
          @click="drink(item)"
        >
          <p>250<br />ml</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const curIdx = ref(0);
    const total = 8;
    const usedCon = computed(() => (curIdx.value / total) * 100);
    const drink = (idx: number) => {
      curIdx.value = idx;
    };
    return {
      curIdx,
      drink,
      usedCon,
    };
  },
});
</script>

<style scoped>
.water-height {
  transition: height 0.3s cubic-bezier(0.39, 0.575, 0.565, 1);
}
</style>