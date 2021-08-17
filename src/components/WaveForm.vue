<template>
  <div class="h-full w-full bg-blue-200 flex justify-center items-center">
    <div class="bg-blue-400 rounded h-2/3 w-1/4">
      <div class="h-1/5 flex justify-center items-center">
        <h1 class="text-3xl text-white font-mono">Please login</h1>
      </div>
      <div class="h-4/5 w-full px-10">
        <div
          class="w-full my-10 text-white font-sans relative"
          v-for="(item, tidx) in titleList"
          :key="tidx"
        >
          <input
            required
            class="
              px-1
              w-full
              text-white
              py-2
              outline-none
              border-b-2 border-white
              input-text-focus
            "
            style="background: none"
          />
          <div class=" absolute top-0">
            <span
              class="text-lg inline-block"
              v-for="(text, idx) in item.split('')"
              :style="{ transitionDelay: idx * 50 + 'ms' }"
              :key="text + idx"
              >{{ text }}</span
            >
          </div>
        </div>
        <!-- <div class="w-full my-10">
          <p class="text-white text-lg font-sans">Password</p>
          <input
            required
            class="
              px-1
              w-full
              text-white
              py-2
              outline-none
              border-b-2 border-white
            "
            style="background: none"
          />
        </div> -->
        <div class="h-14 bg-blue-300 hover:bg-blue-200 w-full px-10">
          <button class="h-full w-full rounded text-white font-mono">
            Login
          </button>
        </div>
        <div class="mt-8 text-white font-sans">
          <span class="space-x-3">Don't have a account?</span
          ><span class="text-blue-500 cursor-pointer hover:text-blue-700"
            >&nbsp;Register</span
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  setup() {
    const titleList = ["Email", "Password"];
    return {
      titleList,
    };
  },
});
</script>

<style scoped>
.input-text-focus:focus ~ div > span {
  transform: translateY(-30px);
	transition: 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
</style>