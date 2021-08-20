<template>
  <div class="bg-white h-full w-full flex justify-center items-center">
    <div
      class="
        h-8
        w-20
        bg-gray-200
        flex
        items-center
        overflow-hidden
        rounded-full
        box-content
        p-1
        botton-box
      "
      :class="{
        'justify-end': ok,
        'justify-start': !ok,
        'bg-gray-200': !ok,
        'bg-yellow-500': ok,
      }"
    >
      <div
        class="cursor-pointer button-self h-8 w-8 p-4 rounded-full"
        :class="{
          'bg-gray-500 hover:bg-yellow-300': !ok,
          'bg-yellow-300 hover:bg-yellow-700': ok,
        }"
        @click="ok = !ok"
      ></div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const ok = ref(false);
    return {
      ok,
    };
  },
});
</script>

<style scoped>
.botton-box, .botton-self {
  transition: all .3s;
}
</style>