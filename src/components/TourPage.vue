<script setup>
  import { ref } from "vue"
  import TourMedia from './TourMedia.vue'
  import TourDescription from './TourDescription.vue'

  const tour = ref({})
</script>

<template>
  <div class="tour-media-container">
    <TourMedia :tour="tour" />
  </div>
  <div class="tour-description-container">
    <TourDescription :tour="tour" />
  </div>
</template>
