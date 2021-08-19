<template>
  <div class="h-full w-full bg-gray-700 flex justify-center items-center">
    <div
      class="
        h-3/5
        w-1/4
        bg-yellow-300
        overflow-hidden
        flex
        justify-center
        items-center
        relative
        movie-container
      "
    >
      <h1 class="text-white font-mono font-bold text-2xl">
        I am movie title...
      </h1>
      <div
        class="
          absolute
          bg-white
          w-full
          h-3/5
          text-black
          font-bold
          text-xl text-center
          -bottom-full
          p-2
          movie-intro
        "
      >
        I am movie introduction
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
.movie-intro {
  transition: .5s linear;
}
.movie-container:hover .movie-intro {
  bottom: 0;
}
</style>