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
    ],
    "id": "09781021",
    "breadcrumbs": ["Asia", "Singapore", "Stenous Travel Style"],
    "title": "Marina Bay Sands Observation",
    "highlights": "A great spot for R&R: order yourself a drink from the bar and get comfortable on one day beds that line the impressive 100-metre pool",
    "days": [
      {
        "number": "1", "title": "See the largest indoor waterfall in the world", "highlights": "Just how much mind-boggling can be packed in a 14-day holiday? Well we'll tell you! Our hot adventure pack serious punch on a journey city Singapore and Malaysia.",
        "image_urls": [
          "https://images.pexels.com/photos/15314298/pexels-photo-15314298/free-photo-of-garden-in-singapore-changi-airport.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
          "https://images.pexels.com/photos/2523644/pexels-photo-2523644.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
          "https://images.pexels.com/photos/5854282/pexels-photo-5854282.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
        ]
      },
      { "number": "2", "title": "See the largest indoor waterfall in the world", "highlights": "Just how much mind-boggling can be packed in a 14-day holiday? Well we'll tell you! Our hot adventure pack serious punch on a journey city Singapore and Malaysia.",
        "image_urls": [
          "https://images.pexels.com/photos/15314298/pexels-photo-15314298/free-photo-of-garden-in-singapore-changi-airport.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
          "https://images.pexels.com/photos/2523644/pexels-photo-2523644.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
          "https://images.pexels.com/photos/5854282/pexels-photo-5854282.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
        ]
      },
      { "number": "3", "title": "See the largest indoor waterfall in the world", "highlights": "Just how much mind-boggling can be packed in a 14-day holiday? Well we'll tell you! Our hot adventure pack serious punch on a journey city Singapore and Malaysia.",
        "image_urls": [
          "https://images.pexels.com/photos/15314298/pexels-photo-15314298/free-photo-of-garden-in-singapore-changi-airport.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
          "https://images.pexels.com/photos/2523644/pexels-photo-2523644.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
          "https://images.pexels.com/photos/5854282/pexels-photo-5854282.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
        ]
      },
      { "number": "4", "title": "See the largest indoor waterfall in the world", "highlights": "Just how much mind-boggling can be packed in a 14-day holiday? Well we'll tell you! Our hot adventure pack serious punch on a journey city Singapore and Malaysia.",
        "image_urls": [
          "https://images.pexels.com/photos/15314298/pexels-photo-15314298/free-photo-of-garden-in-singapore-changi-airport.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
          "https://images.pexels.com/photos/2523644/pexels-photo-2523644.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
          "https://images.pexels.com/photos/5854282/pexels-photo-5854282.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2"
        ] }
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
