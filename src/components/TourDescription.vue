<script setup>
  import 'vue3-carousel/dist/carousel.css'
  import { Carousel, Slide, Navigation } from 'vue3-carousel'
  import RouteIcon from './icons/IconFontAwesomeRoute.vue'

  const props = defineProps({
    tour: Object
  })
</script>

<template>
  <div class="tour-description__wrapper">
    <div class="tour-header">
      <div class="tour-header__references">
        <div class="tour-header__breadcrumbs">
          <ul class="tour-header_breadcrumbs-list">
            <li v-for="item in tour.breadcrumbs">
              <a href="#">{{ item }}</a>
            </li>
          </ul>
        </div>
        <div class="tour-header__tour-id">
          <span>ID: {{ tour.id }}</span>
        </div>
      </div>
    </div>

    <div class="tour-description">
      <div class="tour-description__title">{{ tour.title }}</div>
      <div class="tour-description__highlights">{{ tour.highlights }}</div>
    </div>

    <div class="tour-itinerary__label">
      <span class="tour-itinerary__label-icon">
        <i><RouteIcon /></i>
      </span>
      Itinerary
    </div>

    <div class="tour-itinerary">
      <div class="tour-itinerary__days">
        <div class="tour-itinerary__day" v-for="day in tour.days" :key="day.number">
          <div class="tour-itinerary__day-images-carousel">
            <carousel wrap-around>
              <slide v-for="image_url in day.image_urls" :key="image_url">
                <img v-bind:src="image_url">
              </slide>
              <template #addons>
                <navigation />
              </template>
            </carousel>
          </div>

          <div class="tour-itinerary__day-details-container">
            <div class="tour-itinerary__day-header">
              <span class="tour-itinerary__day-number">Day {{ day.number }}</span>
              <span class="tour-itinenrary__day-title">{{ day.title }}</span>
            </div>
            <div class="tour-itinerary__day-highlights">
              {{ day.highlights }}
            </div>
            <div class="tour-itinenrary__day-show-more">
              Show more
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
  .tour-description__wrapper {
    display: flex;
    flex-direction: column;
    grid-gap: 2rem;
    padding: 1.5rem;

    .tour-header {
      .tour-header__references {
        color: silver;
        display: flex;
        justify-content: space-between;

        .tour-header__breadcrumbs {
          .tour-header_breadcrumbs-list {
            display: flex;
            flex-wrap: wrap;
            list-style: none;
            margin: 0;
            padding: 0;

            a {
              color: silver;

              &:hover {
                background-color: inherit;
                text-decoration: underline;
              }
            }
          }

          .tour-header_breadcrumbs-list li:not(:last-child)::after {
            display: inline-block;
            margin: 0 0.8rem 0 0.8rem;
            content: ">";
          }
        }
      }
    }

    .tour-description {
      .tour-description__title {
        font-size: 1.5rem;
        font-weight: bold;
      }

      .tour-description__highlights {
        font-weight: bold;
      }
    }

    .tour-itinerary__label {
      color: var(--color-dark-blue);
      font-size: 1.5rem;
      font-weight: bold;
      display: inline-block;

      .tour-itinerary__label-icon {
        display: inline-block;
        width: 24px;
        margin-right: 0.5rem;

        svg {
          fill: var(--color-green-blue);
        }
      }
    }

    .tour-itinerary {
      .tour-itinerary__days {
        display: grid;
        position: relative;
        grid-gap: 2rem;
      }

      .tour-itinerary__day {
        display: grid;
        grid-template-columns: 210px 1fr;
        grid-gap: 2rem;
        padding-left: 2rem;

        .tour-itinerary__day-details-container {
          min-height: 100%;
          position: relative;
        }

       .tour-itinerary__day-header {
          span {
            font-weight: bold;
          }

          .tour-itinerary__day-number {
            color: var(--color-dark-blue);
            margin-right: 20px
          }

          .tour-itinenrary__day-title {
            font-size: 18px;
          }
        }

        .tour-itinerary__day-highlights {
          font-size: 14px;
          display: -webkit-box;
          -webkit-box-orient: vertical;
          -webkit-line-clamp: 3;
          overflow: hidden;
          text-overflow: ellipsis;
        }

        .tour-itinenrary__day-show-more {
          color: var(--color-green-blue);
          text-decoration: underline;
          position: absolute;
          bottom: 0;
        }
      }

      .tour-itinerary__day-images-carousel {
        max-height: 140px;
        max-width: 100%;
      }

      .carousel {
        .carousel__item {
          min-height: 200px;
          width: 100%;
          background-color: var(--vc-clr-primary);
          color: var(--vc-clr-white);
          font-size: 20px;
          border-radius: 8px;
          display: flex;
          justify-content: center;
          align-items: center;
        }

        .carousel__slide {
          img {
            height: 140px;
            width: 210px;
            max-height: 100%;
            max-width: 100%;
          }
        }

        .carousel__prev, .carousel__next {
          background-color: var(--vt-c-white);
          border-radius: 1rem;
          font-size: 1rem;
          margin: 0 -12px;
          height: 1.5rem;
          width: 1.5rem;
        }
      }
    }
  }

  @media (max-width: 800px) {
    .tour-description__wrapper .tour-itinerary {
      .tour-itinerary__day {
        display: flex;
        flex-direction: column;

        .tour-itinerary__day-details-container {
          min-height: inherit;

          .tour-itinenrary__day-show-more {
            position: relative;
          }
        }

        img {
          height: 140px;
          width: 210px;
          min-width: 100%;
          object-fit: cover;
        }
      }
    }
  }
</style>
