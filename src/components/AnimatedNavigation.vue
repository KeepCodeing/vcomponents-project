<template>
  <div class="h-full flex justify-center items-center w-full bg-blue-400">
    <nav class="h-16 flex justify-center">
      <ul
        class="
          flex
          font-light
          overflow-hidden
          justify-center
          items-center
          w-0
          h-full
          tab_list
          bg-white
          shadow-lg
        "
        id="tab_list"
      >
        <li
          v-for="(item, idx) in tabList"
          :key="item + idx"
          class="p-2 px-3 h-full flex items-center hover:bg-blue-100"
        >
          <a href="#">{{ item }}</a>
        </li>
      </ul>
      <div
        class="
          p-2
          relative
          cursor-pointer
          px-3
          w-20
          h-full
          flex
          justify-center
          items-center
          oper-button
          bg-white
          shadow-lg
        "
        @click="toggleStatus"
      >
        <div
          class="
            absolute
            h-0.5
            transform
            translate-y-1
            bg-blue-400
            w-5
            border-2 border-blue-400
            line1
            line
          "
          id="line1"
        ></div>
        <div
          class="
            absolute
            h-0.5
            transform
            -translate-y-1
            bg-blue-400
            w-5
            border-2 border-blue-400
            line2
            line
          "
          id="line2"
        ></div>
      </div>
    </nav>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from "vue";

export default defineComponent({
  setup() {
    const tabList = ["Home", "About", "Contact", "Works"];
    type html = HTMLElement | null;
    let line1: html, line2: html, tab_list: html;
    onMounted(() => {
      line1 = document.getElementById("line1");
      line2 = document.getElementById("line2");
      tab_list = document.getElementById("tab_list");
    });

    const toggleStatus = () => {
      if (!line1 || !line2 || !tab_list) return;
      line1.classList.toggle("line_activate");
      line2.classList.toggle("line_activate");
      tab_list.classList.toggle("tab_list_activate");
    };

    return {
      tabList,
      toggleStatus,
    };
  },
});
</script>

<style scoped>
.tab_list {
  transition: width 0.3s linear;
}
.oper-button > .line {
  transition: transform 0.2s linear;
}
.oper-button > .line1.line_activate {
  transform: rotate(-45deg);
}
.oper-button > .line2.line_activate {
  transform: rotate(45deg);
}
.tab_list_activate {
  width: 100%;
}
</style>