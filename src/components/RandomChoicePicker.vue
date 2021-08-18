<template>
  <div class="h-full w-full flex justify-center items-center bg-blue-600">
    <div class="h-2/6 w-5/12">
      <div class="font-mono text-white font-bold text-lg">
        Enter all of the choices divided by a comma (','). Press enter when
        you're done
      </div>
      <div class="w-full h-full mt-2">
        <textarea
          v-model="choices"
          placeholder="Enter choices..."
          class="
            w-full
            h-full
            overflow-x-hidden
            p-2
            focus:outline-none
            resize-none
          "
          @keyup.enter="randomChoices"
        />
        <div class="mt-3">
          <span
            v-for="(item, idx) in choicesList"
            :key="item + idx"
            class="
              rounded-full
              text-white
              font-thin
              text-sm
              bg-yellow-500
              p-2
              mx-2
            "
            :class="{ 'bg-blue-700': curIdx === idx }"
            >{{ item }}</span
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const choices = ref("");
    const choicesList = computed(() =>
      choices.value.split(",").filter((text) => text.trim())
    );
    const curIdx = ref(-1);
    const randomChoices = () => {
      const cLen = choicesList.value.length;
      let cnt: number = 0;
      if (!cLen) return;
      const timer = setInterval(() => {
        if (cnt++ > cLen) {
          clearInterval(timer);
          setTimeout(() => choices.value = "", 1500);
        }
        curIdx.value = Math.floor(Math.random() * cLen);
      }, 100);
      
    };
    return {
      choices,
      choicesList,
      randomChoices,
      curIdx
    };
  },
});
</script>

<style scoped>
</style>