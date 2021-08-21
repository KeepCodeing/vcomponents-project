<template>
  <div class="w-full h-full bg-white flex justify-center items-center">
    <div class="w-80 rounded overflow-hidden bg-gray-100 font-sans shadow-md">
      <div class="h-34 bg-blue-600 text-white p-5">
        <div class="font-bold text-lg text-left">Live User Filter</div>
        <div class="font-light text-sm text-left">
          Search by name and/or location
        </div>
        <div class="w-full mt-5">
          <input
            class="w-full py-2 px-4 bg-blue-700 rounded-full outline-none"
          />
        </div>
      </div>
      <div class="h-96 overflow-y-scroll">
        <ul class="bg-white">
          <li
            class="h-16 border-b-2 border-gray-100 p-1 flex"
            v-for="item in 10"
            :key="item"
          >
            <div class="h-full w-1/4 flex justify-center items-center">
              <div class="rounded-full h-12 w-12 bg-blue-400"></div>
            </div>
            <div class="h-full w-full">
              <div class="h-1/2 w-full">{{ item }} user</div>
              <div class="h-1/2 w-full">{{ item }}</div>
            </div>
          </li>
        </ul>
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