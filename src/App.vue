<template>
  <password-strength-background />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
// import GithubProfiles from './components/GithubProfiles.vue';
// import PasswordGenerateor from './components/PasswordGenerateor.vue';
// import DoubleVerticalSlider from './components/DoubleVerticalSlider.vue';
// import ToastNotification from './components/ToastNotification.vue';
// import FaqCollapse from './components/FaqCollapse.vue';
// import RandomChoicePicker from './components/RandomChoicePicker.vue';
// import HiddenSearchWidget from './components/HiddenSearchWidget.vue';
// import WaveForm from './components/WaveForm.vue';
// import PrograssSteps from '@/components/PrograssSteps.vue'
// import AnimatedNavigation from '@/components/AnimatedNavigation.vue'
// import DrinkWater from './components/DrinkWater.vue';
// import MovieApp from './components/MovieApp.vue';
// import ThemeClock from './components/ThemeClock.vue';
// import RippleButton from '@/components/RippleButton.vue'
// import KineticLoader from '@/components/KineticLoader.vue'
// import ContentPlaceholder from './components/ContentPlaceholder.vue';
// import StickyNavbar from './components/StickyNavbar.vue';
// import SliderButton from '@/components/SliderButton.vue'
// import NotesApp from '@/components/NotesApp.vue'
// import AnimatedCountdown from './components/AnimatedCountdown.vue';
import PasswordStrengthBackground from '@/components/PasswordStrengthBackground.vue'

export default defineComponent({
  components: {
    // HiddenSearchWidget,
    // WaveForm,
    // FaqCollapse,
    // RandomChoicePicker
    // PrograssSteps
    // AnimatedNavigation,
    // DrinkWater,
    // MovieApp,
    // ThemeClock
    // RippleButton,
    // KineticLoader,
    // ContentPlaceholder,
    // StickyNavbar,
    // DoubleVerticalSlider,
    // ToastNotification,
    // GithubProfiles,
    // PasswordGenerateor,
    // SliderButton
    // NotesApp,
    // AnimatedCountdown,
    // MobileTabNavigation
    PasswordStrengthBackground
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
