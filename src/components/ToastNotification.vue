<template>
  <div class="h-full w-full bg-purple-400 flex justify-center items-center">
    <div class="fixed right-3 bottom-3" id="toast"></div>
    <button
      class="
        p-5
        rounded
        hover:
        hover:bg-purple-500 bg-purple-600
        text-white
        font-bold font-sans
      "
      @click="addToast"
    >
      Click Me
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from "vue";

export default defineComponent({
  setup() {
    const toastTypes = ['success', 'warning', 'normal'];
    let toast: HTMLElement | null;
    onMounted(() => toast = document.querySelector('#toast'));
    const addToast = () => {
      const div = document.createElement('div');
      div.classList.add('bg-white');
      div.classList.add('text-green-300')
      div.classList.add('mt-4');
      div.classList.add('p-5');
      div.classList.add('rounded');
      div.innerText = 'Hello world';
      toast?.append(div);
      setTimeout(() => div.remove(), 3000);
    }
    return {
      addToast,
    };
  },
});
</script>

<style scoped>
</style>