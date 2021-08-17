<template>
  <div class="h-full w-full bg-purple-300 flex justify-center items-center">
    <div class="w-60 h-14 flex justify-end rounded-md">
      <div
        style="transition: 500ms"
        :class="hiddenInput ? 'w-0' : 'w-4/5'"
        class="h-full"
      >
        <input
          class="
            w-full
            pl-2
            rounded-tl-md rounded-bl-md
            outline-none
            text-gray-300
            h-full
          "
          placeholder="Search..."
        />
      </div>
      <div
        :class="{ 'rounded-md': hiddenInput }"
        style="transition: 1000ms"
        class="w-1/5 bg-white rounded-tr-md rounded-br-md text-center h-full"
      >
        <button @click="hiddenInput = !hiddenInput" class="h-full">
          <svg
            t="1629183641204"
            class="icon"
            viewBox="0 0 1024 1024"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            p-id="2115"
            width="30"
            height="30"
          >
            <path
              d="M400.704 801.408A400.64 400.64 0 1 1 400.704 0a400.64 400.64 0 0 1 0 801.408z m0-89.024a311.68 311.68 0 1 0 0-623.36 311.68 311.68 0 0 0 0 623.36z m267.264-110.4l314.752 314.88-62.912 62.912-314.816-314.816 62.976-62.976z"
              fill="#1C1C1C"
              p-id="2116"
            ></path>
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const hiddenInput = ref(true);
    return {
      hiddenInput,
    };
  },
});
</script>

<style scoped>
</style>