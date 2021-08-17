<template>
  <wave-form />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
// import HiddenSearchWidget from './components/HiddenSearchWidget.vue';
import WaveForm from './components/WaveForm.vue';
// import PrograssSteps from '@/components/PrograssSteps.vue'

export default defineComponent({
  components: {
    // HiddenSearchWidget,
    WaveForm
    // PrograssSteps
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
