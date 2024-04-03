<script setup>
  import 'vue3-carousel/dist/carousel.css'
  import { Carousel, Slide, Navigation } from 'vue3-carousel'

  import VuePlyr from 'vue-plyr'
  import 'vue-plyr/dist/vue-plyr.css'

  const props = defineProps({
    tour: Object
  })
</script>

<template>
  <div class="tour-preview__carousel">
    <Carousel :wrap-around="true" :breakpoints="breakpoints" :items-to-show="1.2">
      <Slide :key="tour.video_url">
        <vue-plyr>
          <div class="plyr__video-embed">
            <iframe :src="tour.video_url" allowfullscreen allowtransparency allow="autoplay"></iframe>
          </div>
        </vue-plyr>
      </Slide>

      <Slide v-for="image_url in tour.image_urls" :key="image_url">
        <div class="tour-preview__carousel-image-wrapper">
          <img v-bind:src="image_url"></img>
        </div>
      </Slide>

      <template #addons>
        <Navigation />
      </template>
    </Carousel>
  </div>
</template>

<style>
  .tour-preview__carousel {
    .tour-preview__carousel-image-wrapper {
      height: 400px;
      min-width: 100%;
      background-color: var(--vc-clr-primary);
      color: var(--vc-clr-white);
      border-radius: 8px;

      img {
        height: 400px;
        min-width: 100%;
        object-fit: cover;
      }
    }

    .carousel__slide {
      padding: 0.4rem;
    }

    .carousel__prev, .carousel__next {
      background-color: var(--vt-c-white);
      border-radius: 1rem;
      font-size: 1rem;
      margin: 0 10%;
      height: 1.5rem;
      width: 1.5rem;
    }
  }

  .plyr {
    height: 400px;
    min-width: 100%;
  }

  .plyr__video-embed {
    min-height: 100%;
  }

  .plyr:not(:fullscreen) {
    .plyr__video-embed {
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
    }
  }

  @media (max-width: 800px) {
    .tour-preview__carousel .carousel__slide {
      padding: 0;
      margin-right: -1px;
    }
  }
</style>
