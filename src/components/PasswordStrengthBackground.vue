<template>
  <div
    class="
      h-full
      w-full
      flex
      font-sans
      justify-center
      items-center
    "
    :class="'bg-yellow-' + (password.length >= 9 ? 900 : password.length * 100)"
  >
    <div class="h-3/5 w-1/3 bg-white p-8 rounded">
      <div class="text-3xl text-black text-center">Image Password Strength</div>
      <div class="text-sm font-light mt-1 text-black text-center">
        Change the password to see the effect
      </div>
      <form class="mt-5">
        <div>
          <label>Emali:</label>
          <input
            class="w-full mt-2 border-2 p-2 outline-none"
            placeholder="Enter Email"
          />
        </div>
        <div class="mt-5">
          <label>Password:</label>
          <input
            class="w-full mt-2 border-2 p-2 outline-none"
            type="password"
            placeholder="Enter password"
            v-model="password"
          />
        </div>
      </form>
      <div class="w-full mt-10">
        <button class="p-3 w-full bg-black text-white font-light rounded">Submit</button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const password = ref('');
    return {
      password,
    };
  },
});
</script>

<style scoped>
</style>