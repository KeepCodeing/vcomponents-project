<template>
  <div class="h-full w-full bg-gray-100">
    <div
      class="
        w-full
        h-14
        fixed
        bottom-0
        py-2
        bg-white
        flex
        justify-around
        items-center
      "
    >
      <div class="h-full flex flex-col items-center" v-for="item in 4" :key="item">
        <svg t="1629517117788" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2095" width="22" height="22"><path d="M971.6736 445.2352L594.8416 53.3504a122.2656 122.2656 0 0 0-176.5376 0L41.5744 445.2352c-38.912 40.96-33.8944 75.4688-27.5456 90.0096a65.536 65.536 0 0 0 64.6144 38.912h55.296v301.4656c0 68.4032 49.152 133.12 119.0912 133.12h160.3584V689.4592c0-34.2016-5.12-53.248 29.7984-53.248h126.7712c35.0208 0 29.7984 19.0464 29.7984 53.248v319.0784h160.4608c69.8368 0 119.0912-64.512 119.0912-133.12V574.1568h55.1936a65.536 65.536 0 0 0 64.6144-38.912c6.4512-14.5408 11.4688-49.5616-27.4432-90.0096z" fill="#2c2c2c" p-id="2096"></path></svg>
        <span class=" text-xs font-light">Home</span>
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
</style>