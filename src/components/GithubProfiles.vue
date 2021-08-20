<template>
  <div class="h-full w-full bg-purple-500 flex justify-center items-center">
    <div
      class="
        w-2/4
        box-content
        flex-col flex
        justify-start
        items-center
        h-2/3
        p-2
      "
    >
      <div class="w-4/5 h-16 overflow-hidden rounded-full">
        <input
          class="
            w-full
            outline-none
            h-full
            pl-4
            placeholder-white
            text-white
            bg-purple-700
          "
          placeholder="Search Github User"
        />
      </div>
      <div
        class="
          mt-10
          rounded-lg
          p-3
          w-full
          h-72
          bg-purple-700
          grid grid-cols-12 grid-rows-6
        "
      >
        <div
          class="
            col-span-2
            row-start-2 row-span-3
            border-4
            bg-yellow-300
            rounded-full
            flex
            p-16
          "
        ></div>
        <div class="row-start-2 col-start-4 col-span-6 row-span-1">
          <h1 class="font-bold font-sans text-white text-2xl">KeepCoding</h1>
        </div>
        <div class="row-start-3 col-start-4 col-span-6 row-span-1">
          <h1 class="font-sans text-white text-base">Something boring...</h1>
        </div>
        <div class="row-start-4 col-start-4 col-span-6 row-span-1">
          <div class="h-full text-white font-sans w-full flex justify-between">
            <h3>4 <span class="font-bold">Flowers</span></h3>
            <h3>5 <span class="font-bold">Following</span></h3>
            <h3>33 <span class="font-bold">Repos</span></h3>
          </div>
        </div>
        <div class="row-start-5 col-start-4 col-span-10 row-span-1">
          <div class="text-white break-all font-sans">
            <span
              class="px-2 py-1 font-light m-1 inline-block bg-purple-900 text-sm text-white"
              >vcomponents-projects</span
            >
            <span
              class="px-2 py-1 font-light m-1 inline-block bg-purple-900 text-sm text-white"
              >LearnTypeScript</span
            >
            <span
              class="px-2 py-1 font-light m-1 inline-block bg-purple-900 text-sm text-white"
              >qingzhou-unet</span
            >
            <span
              class="px-2 py-1 font-light m-1 inline-block bg-purple-900 text-sm text-white"
              >Smart-Logistics</span
            >
            <span
              class="px-2 py-1 font-light m-1 inline-block bg-purple-900 text-sm text-white"
              >Cookie-Project</span
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>