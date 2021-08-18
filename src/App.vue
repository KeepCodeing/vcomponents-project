<template>
  <animated-navigation />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
// import FaqCollapse from './components/FaqCollapse.vue';
// import RandomChoicePicker from './components/RandomChoicePicker.vue';
// import HiddenSearchWidget from './components/HiddenSearchWidget.vue';
// import WaveForm from './components/WaveForm.vue';
// import PrograssSteps from '@/components/PrograssSteps.vue'
import AnimatedNavigation from '@/components/AnimatedNavigation.vue'

export default defineComponent({
  components: {
    // HiddenSearchWidget,
    // WaveForm,
    // FaqCollapse,
    // RandomChoicePicker
    // PrograssSteps
    AnimatedNavigation
  }
});
</script>

<style>
* {
  padding: 0;
  margin: 0;
}
html, body, #app {
  height: 100%;
  width: 100%;
}
</style>
