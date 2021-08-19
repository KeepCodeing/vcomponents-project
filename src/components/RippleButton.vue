<template>
  <div class="bg-black h-full w-full flex justify-center items-center">
    <div>
      <button
        @click="appendCircle"
        id="bt"
        class="
          p-4
          cursor-pointer
          overflow-hidden
          relative
          rounded
          bg-yellow-400
          text-white
        "
      >
        Click Me
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from "vue";

export default defineComponent({
  setup() {
    let bt: HTMLElement | null;
    onMounted(() => (bt = document.querySelector("#bt")));

    const appendCircle = (e: any) => {
      if (!bt) return;
      const div = document.createElement("div");
      div.classList.add("circle");
      div.style.top = e.clientY - e.target.offsetTop + "px";
      div.style.left = e.clientX - e.target.offsetLeft + "px";

      bt.append(div);

      setTimeout(() => div.remove(), 500);
    };

    return {
      appendCircle,
    };
  },
});
</script>

<style>
@keyframes sca {
  to {
    opacity: 0;
    transform: scale(5);
  }
}
.circle {
  position: absolute;
  transform: translate(-50%);
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.7);
  height: 50px;
  width: 50px;
  transition: cubic-bezier(0.075, 0.82, 0.165, 1);
  animation: sca 0.5s;
}
</style>