<template>
  <div class="h-full w-full flex justify-center items-center bg-yellow-100">
    <div class="shadow-md w-96 bg-white p-5 font-sans">
      <div v-show="!hiddenFeed" class="w-full">
        <div
          class="
            w-full
            b-gyellow-200
            text-black text-center
            font-medium
            text-base
          "
        >
          How satisfied are you with our<br />
          customer support performance?
        </div>
        <div class="w-full mt-10 flex justify-between items-center">
          <div
            v-for="item in feedList"
            :key="item"
            class="
              w-1/3
              flex
              items-end
              justify-center
              h-28
              cursor-pointer
              hover:shadow-md
              hover:bg-green-300
              bg-yellow-300
              mx-2
              p-2
            "
            :class="{ 'bg-green-300': curFeed === item }"
            @click="curFeed = item"
          >
            <div class="text-black font-light">{{ item }}</div>
          </div>
        </div>
        <div class="w-full mt-10 text-center">
          <button
            @click="hiddenFeed = true"
            class="bg-black rounded text-sm text-white py-3 px-5 fbutton"
          >
            Send Review
          </button>
        </div>
      </div>
      <div v-show="hiddenFeed" class="w-full">
        <div class="flex justify-center items-center flex-col font-medium">
          <svg
            t="1629536646877"
            class="icon"
            viewBox="0 0 1024 1024"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            p-id="3029"
            width="26"
            height="26"
          >
            <path
              d="M489.984 887.104l-312.096-301.088c-4-3.488-114.048-104.032-114.048-224.064 0-146.528 89.536-234.08 239.072-234.08 87.52 0 169.536 69.024 209.056 108.032 39.52-39.008 121.536-108.032 209.056-108.032 149.536 0 239.072 87.52 239.072 234.08 0 120.032-110.016 220.576-114.528 225.056l-311.584 300.096c-6.016 6.016-14.016 8.992-22.016 8.992s-16-3.008-22.016-8.992z"
              p-id="3030"
              fill="#d81e06"
            ></path>
          </svg>
          <p class="mt-2">Thank You!</p>
          <p class="mt-3">Feedback: {{ curFeed }}</p>
          <p class="mt-7 font-light text-gray-500 text-center">
            We'll use your feedback to improve our<br />
            customer support!
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const feedList = ["Unhappy", "Neutral", "Satisfied"];
    const hiddenFeed = ref(false);
    const curFeed = ref('');
    return {
      feedList,
      hiddenFeed,
      curFeed,
    };
  },
});
</script>

<style scoped>
.fbutton:active {
  transition: transform 0.1s cubic-bezier(0.39, 0.575, 0.565, 1);
  transform: scale(0.95);
}
</style>