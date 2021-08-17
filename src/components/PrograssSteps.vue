<template>
  <div class="h-full bg-gray-100 w-full flex justify-center items-center">
    <div class="h-36 relative w-2/5 flex items-center justify-between rounded">
      <div
        v-for="item in totalStep"
        @click="calPrograss(item)"
        style="transition: 300ms"
        :class="{ 'border-blue-300': item <= cur }"
        class="
          flex
          z-10
          items-center
          justify-center
          h-8
          w-8
          border-2 border-gray-300
          rounded-full
          bg-white
          text-gray-500 text-sm
          cursor-pointer
        "
        :key="item"
      >
        {{ item }}
      </div>
      <div
        class="
          h-1
          w-full
          absolute
          top-1/2
          transform
          bg-gray-200
          left-1/2
          -translate-x-1/2 -translate-y-1/2
        "
      ></div>
      <!-- 或者用before等伪元素 -->
      <div
        id="prograss"
        style="transition: 300ms"
        class="h-1 absolute top-1/2 transform bg-blue-300 -translate-y-1/2"
      ></div>
      <div
        class="w-full flex align-bottom justify-around h-1/3 bottom-0 absolute"
      >
        <button
          @click="calCur(cur, 'prev')"
          :disabled="cur === 1"
          class="py-1 px-3 text-white rounded-md bg-blue-300 hover:bg-blue-200"
        >
          prev
        </button>
        <button
          @click="calCur(cur, 'next')"
          :disabled="cur === totalStep"
          class="py-1 px-3 text-white rounded-md bg-blue-300 hover:bg-blue-200"
        >
          next
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, ref } from "vue";

export default defineComponent({
  setup() {
    const totalStep = ref(6);
    const cur = ref(1);
    let prograss: HTMLElement | null;
    onMounted(() => {
      prograss = document.getElementById("prograss");
    });

    const calPrograss = (idx: number) => {
      if (!prograss) return;
      // 同时-1防止宽度出错
      prograss.style.width = ((idx - 1) / (totalStep.value - 1)) * 100 + "%";
      cur.value = idx;
    };
    const calCur = (curIdx: number, mode: string) => {
      if (mode === "prev") cur.value += curIdx <= 1 ? 0 : -1;
      else cur.value += curIdx >= totalStep.value ? 0 : 1;
      calPrograss(cur.value);
    };

    return {
      totalStep,
      calPrograss,
      cur,
      calCur,
    };
  },
});
</script>

<style scoped>
</style>