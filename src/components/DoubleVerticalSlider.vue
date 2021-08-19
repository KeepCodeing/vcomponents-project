<template>
  <div class="h-full flex overflow-hidden w-full">
    <div class="h-full relative color-list w-1/3">
      <button
        @click="moveList('left')"
        class="absolute z-10 bg-yellow-500 right-0 p-2"
        :style="'top: 50.7%'"
      >
        <svg
          t="1629359115090"
          class="icon"
          viewBox="0 0 1024 1024"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          p-id="2069"
          width="25"
          height="25"
        >
          <path
            d="M864.542276 623.970572l-44.031214-42.4221a45.859753 45.859753 0 0 0-64.657131 0.731416l-166.177604 167.640435V47.542008A47.030017 47.030017 0 0 0 543.012018 0h-62.170319a47.030017 47.030017 0 0 0-46.518026 47.542008v702.451456L268.146069 582.353029a45.859753 45.859753 0 0 0-64.657131-0.731415l-42.495241 40.959268a48.273424 48.273424 0 0 0-7.094731 60.414922l6.58274 8.191853 333.159765 331.258085c12.141497 2.047963 24.648703 2.047963 36.863341 0L863.591436 691.187657a48.273424 48.273424 0 0 0 0.877698-67.217085z"
            p-id="2070"
          ></path>
        </svg>
      </button>
      <div
        class="h-full color-list w-full"
        :style="'transform: translateY(-' + curIdx * 100 + '%)'"
      >
        <div
          class="w-full h-full"
          v-for="color in leftList"
          :key="color"
          :class="color"
        ></div>
      </div>
    </div>
    <div class="h-full w-2/3 relative">
      <button
        @click="moveList('right')"
        class="absolute z-10 bg-yellow-500 left-0 p-2"
        style="top: 45%"
      >
        <svg
          t="1629359115090"
          class="icon transform rotate-180"
          viewBox="0 0 1024 1024"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          p-id="2069"
          width="25"
          height="25"
        >
          <path
            d="M864.542276 623.970572l-44.031214-42.4221a45.859753 45.859753 0 0 0-64.657131 0.731416l-166.177604 167.640435V47.542008A47.030017 47.030017 0 0 0 543.012018 0h-62.170319a47.030017 47.030017 0 0 0-46.518026 47.542008v702.451456L268.146069 582.353029a45.859753 45.859753 0 0 0-64.657131-0.731415l-42.495241 40.959268a48.273424 48.273424 0 0 0-7.094731 60.414922l6.58274 8.191853 333.159765 331.258085c12.141497 2.047963 24.648703 2.047963 36.863341 0L863.591436 691.187657a48.273424 48.273424 0 0 0 0.877698-67.217085z"
            p-id="2070"
          ></path>
        </svg>
      </button>
      <div
        class="w-full color-list h-full"
        :style="'transform: translateY(-' + ((listLen - 1) * 100 - curIdx * 100) + '%)'"
      >
        <div
          class="w-full h-full"
          v-for="color in rightList"
          :key="color"
          :class="color"
        ></div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, toRef } from "vue";

export default defineComponent({
  setup() {
    const leftList = ref([
      "bg-yellow-300",
      "bg-red-300",
      "bg-purple-300",
      "bg-blue-300",
    ]);
    // 注意这里用了slice对数组进行一个类似复制的操作，如果不这样reverse会改变原数组
    // 也就是说两个数组都会被翻转...
    // const rightList = ref(leftList.value.slice().reverse());
    const rightList = ref([
      "bg-indigo-300",
      "bg-black",
      "bg-green-300",
      "bg-purple-300",
    ])

    const curIdx = ref(0);
    const listLen = leftList.value.length;

    const moveList = (ty: string) => {
      curIdx.value += ty === "left" ? -1 : 1;
      if (curIdx.value < 0) curIdx.value = listLen - 1;
      else if (curIdx.value >= listLen) curIdx.value = 0;
    };

    return {
      moveList,
      leftList,
      rightList,
      curIdx,
      listLen,
    };
  },
});
</script>

<style scoped>
.color-list {
  transition: transform 0.3s cubic-bezier(0.075, 0.82, 0.165, 1);
}
</style>