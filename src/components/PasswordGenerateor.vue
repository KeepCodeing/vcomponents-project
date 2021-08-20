<template>
  <div class="bg-yellow-500 h-full w-full flex justify-center items-center">
    <div class="p-6 grid grid-cols-1 w-80 shadow bg-yellow-300 gen-box">
      <div class="text-center text-white text-2xl font-bold font-sans">
        Password Generateor
      </div>
      <div class="bg-yellow-400 flex justify-between p-1">
        <div class="w-5/6 p-2 h-full text-white" v-text="pwd" />
        <div
          class="
            hover:bg-yellow-500
            cursor-pointer
            w-1/6
            h-full
            flex
            p-2
            items-center
            justify-center
            bg-yellow-200
          "
        >
          <svg
            t="1629438908991"
            class="icon"
            viewBox="0 0 1024 1024"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            p-id="6548"
            width="28"
            height="28"
          >
            <path
              d="M586.794667 277.034667h-149.589334A95.744 95.744 0 0 1 357.632 234.666667H266.666667a32 32 0 0 0-31.701334 27.648L234.666667 266.666667v576.213333c0 16.213333 12.032 29.568 27.648 31.701333l8.704 0.554667a32 32 0 0 1-4.352 63.744 96 96 0 0 1-95.786667-89.429333L170.666667 842.88V266.666667a96 96 0 0 1 89.429333-95.786667L266.666667 170.666667h75.221333a95.872 95.872 0 0 1 95.317333-85.333334h149.589334c49.408 0 90.026667 37.333333 95.317333 85.333334h75.221333a96 96 0 0 1 95.786667 89.429333L853.333333 266.666667v234.837333a32 32 0 0 1-63.701333 4.352l-0.298667-4.352V266.666667a32 32 0 0 0-27.648-31.701334L757.333333 234.666667h-90.965333c-17.194667 25.6-46.421333 42.368-79.573333 42.368zM725.333333 597.248h42.666667a170.666667 170.666667 0 0 1 8.704 341.12l-8.533333 0.213333-42.666667 0.170667a42.666667 42.666667 0 0 1-5.333333-85.034667l4.949333-0.298666L768 853.205333a85.333333 85.333333 0 0 0 6.4-170.410666l-6.4-0.213334h-42.666667a42.666667 42.666667 0 0 1-4.992-85.077333l4.992-0.256h42.666667-42.666667z m-192 0.170667h42.666667a42.666667 42.666667 0 0 1 4.992 85.034666l-4.992 0.298667h-42.666667a85.333333 85.333333 0 0 0-6.4 170.453333l6.4 0.213334h42.666667a42.666667 42.666667 0 0 1 4.992 85.034666l-4.992 0.298667h-42.666667a170.666667 170.666667 0 0 1-8.533333-341.12l8.533333-0.213333h42.666667-42.666667zM533.290667 725.333333H768a42.666667 42.666667 0 0 1 4.992 85.034667L768 810.666667h-234.709333a42.666667 42.666667 0 0 1-4.992-85.077334l4.992-0.256H768h-234.709333z m53.504-576h-149.589334a31.872 31.872 0 1 0 0 63.701334h149.589334a31.872 31.872 0 1 0 0-63.701334z"
              p-id="6549"
              fill="#ffffff"
            ></path>
          </svg>
        </div>
      </div>

      <div class="text-white flex justify-between items-center">
        <span class="w-4/5">Password Length</span
        ><input
          v-model="pwdLen"
          max="20"
          min="1"
          type="number"
          class="text-black pl-2 w-1/5 outline-none"
        />
      </div>

      <div
        class="text-white flex justify-between items-center"
        v-for="(item, idx) in choices"
        :key="item.title"
      >
        <span class="w-4/5">{{ item.title }}</span>
        <div class="text-right w-1/5">
          <input
            v-if="choices[idx]"
            v-model="choices[idx].checked"
            type="checkbox"
            class="text-black pl-2 border-gray-400"
          />
        </div>
      </div>

      <div class="w-full">
        <button
          class="p-2 bg-yellow-400 text-white font-sans font-medium w-full"
          @click="genPwd"
        >
          Generate Password
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref } from "vue";

export default defineComponent({
  setup() {
    const pwdLen = ref(20);
    const pwd = ref("");
    const getRandomChar = (st: number, limit: number) =>
      String.fromCharCode(Math.floor(Math.random() * limit) + st);
    const choices = reactive([
      {
        title: "Include uppercase letters",
        checked: true,
        type: "up",
        fun: (st: number = 65, limit: number = 26) => getRandomChar(st, limit),
      },
      {
        title: "Include lowercase letters",
        checked: true,
        type: "low",
        fun: (st: number = 97, limit: number = 26) => getRandomChar(st, limit),
      },
      {
        title: "Include numbers",
        checked: true,
        type: "num",
        fun: (st: number = 48, limit: number = 10) => getRandomChar(st, limit),
      },
      {
        title: "Include symbols",
        checked: true,
        type: "sym",
        fun: (st: number = 33, limit: number = 14) => getRandomChar(st, limit),
      },
    ]);

    const genPwd = () => {
      pwd.value = "";
      const temp_choices = choices.filter((item) => item.checked);
      for (let i = 0; i < 20; i++)
        pwd.value += temp_choices.map((item) => item.fun());
      pwd.value = pwd.value.substr(0, pwdLen.value);
    };

    return {
      choices,
      pwdLen,
      pwd,
      genPwd,
    };
  },
});
</script>

<style scoped>
.gen-box > div {
  @apply my-2;
}
</style>