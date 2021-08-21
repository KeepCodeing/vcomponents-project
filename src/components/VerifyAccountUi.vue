<template>
  <div
    class="h-full w-full bg-white flex justify-center font-sans items-center"
  >
    <div class="h-3/6 w-2/3 rounded-lg py-10 border-2 border-black">
      <div class="text-2xl text-black font-medium text-center">
        Verify Your Account
      </div>
      <div class="text-sm mt-1 text-black font-light text-center">
        We emailed you the six digit code to cool_guy@email.com<br />
        Enter the codebelow to confirm your email address.
      </div>
      <div class="text-center mt-5">
        <input
          class="
            p-1
            h-32
            text-7xl
            focus:ring-2
            focus:ring-blue-300
            focus:border-opacity-0
            outline-none
            w-32
            m-2
            text-center
            border-black border-2
            ver-input
          "
          required
          min="0"
          max="9"
          maxlength="1"
          placeholder="0"
          v-for="item in 6"
          :key="item"
          @input="move2next(item - 1)"  
        />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from "vue";

export default defineComponent({
  setup() {
    let inputList: NodeListOf<HTMLInputElement> | null;
    onMounted(() => {
      inputList = document.querySelectorAll('.ver-input');
      inputList[0].focus();
    })
    const move2next = (idx: number) => {
      if (!inputList) return;
      if (idx + 1 >= inputList.length) return;
      setTimeout(() => inputList && inputList[idx + 1].focus(), 100);
    }
    return {
      move2next
    };
  },
});
</script>

<style scoped>
</style>