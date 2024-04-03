<script setup>
  import { ref } from "vue"
  import TourMedia from './TourMedia.vue'
  import TourDescription from './TourDescription.vue'

  import tourData from '../../data/tour.json'
  const tour = ref(tourData)
</script>

<template>
  <div class="tour-media-container">
    <TourMedia :tour="tour" />
  </div>
  <div class="tour-description-container">
    <TourDescription :tour="tour" />
  </div>
</template>

<style scoped>
  .tour-description-container {
    background-color: var(--vt-c-white);
    background-clip: content-box;
    position: relative;
    margin-top: -3.5rem;
    padding: 0 10% 0 10%;
    z-index: 1;
  }
</style>
