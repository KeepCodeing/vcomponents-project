<template>
  <div style="height: 300vh" class="w-full bg-yellow-300">
    <nav
      id="nav"
      class="fixed px-10 top-0 w-full flex justify-between items-center"
      :class="{ 'bg-white h-12': scrollOut, 'bg-black h-16': !scrollOut }"
    >
      <div>
        <h1
          class="font-sans text-xl"
          :class="{ 'text-white': !scrollOut, 'text-black': scrollOut }"
        >
          Web Blog
        </h1>
      </div>
      <div>
        <a
          v-for="item in tabs"
          :key="item"
          class="
            hover:text-red-600
            cursor-pointer
            mx-3
            font-sans
            inline-block
            font-thin
          "
          :class="{ 'text-white': !scrollOut, 'text-black': scrollOut }"
        >
          {{ item }}
        </a>
      </div>
    </nav>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, ref } from "vue";

export default defineComponent({
  setup() {
    const tabs = ["Home", "About", "Contact", "Service"];
    const scrollOut = ref(false);
    onMounted(() => {
      const nav: HTMLElement | null = document.querySelector("#nav");
      window.addEventListener("scroll", () => {
        if (!nav) return;
        if (window.scrollY > nav.offsetHeight + 150) scrollOut.value = true;
        else scrollOut.value = false;
      });
    });

    return {
      tabs,
      scrollOut,
    };
  },
});
</script>

<style scoped>
#nav {
  transition: all 0.2s linear;
}
</style>