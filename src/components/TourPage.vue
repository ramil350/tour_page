<script setup>
  import { ref } from "vue"
  import TourMedia from './TourMedia.vue'
  import TourDescription from './TourDescription.vue'

  const tour = ref({
    "video_url": "https://www.youtube.com/watch?v=_166VGD6kLs",
    "image_urls": [
      "https://images.pexels.com/photos/1842332/pexels-photo-1842332.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
      "https://images.pexels.com/photos/5414577/pexels-photo-5414577.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
      "https://images.pexels.com/photos/11777903/pexels-photo-11777903.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
      "https://images.pexels.com/photos/12936034/pexels-photo-12936034.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
    ]
  })
</script>

<template>
  <div class="tour-media-container">
    <TourMedia :tour="tour" />
  </div>
  <div class="tour-description-container">
    <TourDescription :tour="tour" />
  </div>
</template>
