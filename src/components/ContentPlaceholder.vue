<template>
  <div class="bg-gray-200 h-full w-full flex justify-center items-center">
    <div
      class="w-3/12 shadow pb-4 overflow-hidden rounded bg-white"
      :class="{ 'h-2/3': isLoading }"
    >
      <div
        class="w-full"
        :class="{
          'bg-gray-200 animate-pulse h-1/2': isLoading,
          'h-48 bg-yellow-300': !isLoading,
        }"
      ></div>
      <div class="h-1/2 w-full px-6 mt-6">
        <div
          class="w-full mb-10"
          :class="{ 'animate-pulse rounded-full bg-gray-200 h-2': isLoading }"
        >
          <h2 class="text-xl fong-bold" v-show="!isLoading">
            {{ content.title }}
          </h2>
        </div>
        <div
          v-show="isLoading"
          v-for="item in 3"
          :key="item"
          class="rounded-full bg-gray-200 mb-3 animate-pulse w-full h-2"
        ></div>
        <div v-show="!isLoading" class="mb-3 w-full">{{ content.text }}</div>
        <div class="grid grid-cols-12 gap-2 mt-10 grid-row-2">
          <div
            class="p-6 flex rounded-full row-span-2 col-span-2"
            :class="{
              'animate-pulse bg-gray-200': isLoading,
              'bg-yellow-300': !isLoading,
            }"
          ></div>
          <div
            class="col-span-10 h-2 row-span-1 font-bold"
            :class="{ 'bg-gray-200 mt-2 rounded-full animate-pulse': isLoading }"
          >
            <h2 v-show="!isLoading">{{ content.creator }}</h2>
          </div>
          <div
            class="col-span-10 h-2 row-span-1"
            :class="{ 'bg-gray-200 animate-pulse rounded-full': isLoading }"
          ><p v-show="!isLoading">{{ content.date }}</p></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, reactive } from "vue";

export default defineComponent({
  setup() {
    const isLoading = ref(true);
    const content = reactive({
      title: "今天也是好天气！",
      text: "RIM你又在偷懒啦！休息中哟...今天一定是休息日啦！那明天呢？Jinja闭店之日！",
      creator: "UDK",
      date: "1919.5.14",
    });
    setTimeout(() => (isLoading.value = false), 300);
    return {
      isLoading,
      content,
    };
  },
});
</script>

<style scoped>
</style>