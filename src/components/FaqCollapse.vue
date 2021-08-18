<template>
  <div class=" min-h-full w-full bg-yellow-50 flex justify-center items-center">
    <div class="h-full w-5/12">
      <div
        class="
          h-28
          p-3
          my-5
          rounded
          grid grid-cols-5 grid-rows-3
          border-2
          w-full
          bg-gray-100
          font-mono font-bold
          text-2xl
          faq
        "
        v-for="(item, idx) in questions"
        :key="idx"
      >
        <div class="col-span-4 row-span-1 text-left">
          {{ item.title }}
        </div>
        <div @click="activateFaq(idx)" class="col-span-1 row-span-1 text-right">
          <svg
            t="1629250864203"
            class="icon inline-block cursor-pointer"
            viewBox="0 0 1024 1024"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            p-id="2068"
            width="30"
            height="30"
          >
            <path
              d="M512 64a448 448 0 1 1 0 896A448 448 0 0 1 512 64zM408.576 363.136a32 32 0 1 0-45.312 45.248l103.808 103.744-103.808 103.744a32 32 0 1 0 45.312 45.248l103.744-103.68 103.744 103.68a32 32 0 1 0 45.248-45.248l-103.744-103.68 103.744-103.808a32 32 0 0 0-45.248-45.248L512.32 466.88z"
              fill="#bfbfbf"
              p-id="2069"
            ></path>
          </svg>
        </div>
        <div class="col-span-5 content hidden mt-6 row-span-2">{{ item.content }} </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, reactive } from "vue";

export default defineComponent({
  setup() {
    const questions = reactive([
      { title: "Why shouldn't we trust atoms?", content: "They make up everything." },
      { title: "What do you call someone with no body and no nose?", content: "Nobody knows." },
      { title: "What's the object-oriented way to become wealthy?", content: "Inheritance." },
      { title: "How many tickles does it take to tickle an octopus?", content: "Ten-tickles!" },
    ]);

    let faqs: HTMLCollection | null = null;

    onMounted(() => {
      faqs = document.getElementsByClassName('faq');
    })

    const activateFaq = (idx: number) => {
      if (!faqs) return;
      const isAct = faqs[idx].classList.contains('activate')
      if (!isAct) faqs[idx].classList.add('activate');
      else faqs[idx].classList.remove('activate');
    }
    return {
      questions,
      activateFaq
    };
  },
});
</script>

<style scoped>
.faq {
  /* transition: .3s cubic-bezier(0.075, 0.82, 0.165, 1); */
}
.faq.activate {
  background-color: white;
  @apply h-48;
}
.faq.activate > .content {
  display: block;
}
</style>