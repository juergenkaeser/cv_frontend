<script setup>
import ProjectItem from './ProjectItem.vue'
import { onMounted, defineProps } from 'vue'
import Glide, { Controls } from '@glidejs/glide/dist/glide.modular.esm'
import data from '../assets/data.json';

defineProps({
  fontColorSecondary: {
    type: String,
    default: '',
    required: true
  }
});

onMounted(() => {
  new Glide('.glide', {
    type: 'carousel'
  }).mount({ Controls })
})
</script>

<template>
  <div class="glide">
    <div class="glide__track" data-glide-el="track">
      <ul class="glide__slides">
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>{{ data.projects[0].headline }}</template>
            <template #subline>{{ data.projects[0].subline }}</template>
            {{ data.projects[0].description }}
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>{{ data.projects[1].headline }}</template>
            <template #subline>{{ data.projects[1].subline }}</template>
            {{ data.projects[1].description }}
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>{{ data.projects[2].headline }}</template>
            <template #subline>{{ data.projects[2].subline }}</template>
            {{ data.projects[2].description }}
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>{{ data.projects[3].headline }}</template>
            <template #subline>{{ data.projects[3].subline }}</template>
            {{ data.projects[3].description }}
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>{{ data.projects[4].headline }}</template>
            <template #subline>{{ data.projects[4].subline }}</template>
            {{ data.projects[4].description }}
            <br />
            <br />
            <a href="https://github.com/juergenkaeser/cv_frontend" target="_blank"
              >Projekt auf GitHub</a
            >
          </ProjectItem>
        </li>
      </ul>
      <div class="glide__bullets" data-glide-el="controls[nav]">
        <button class="glide__bullet" data-glide-dir="=0"></button>
        <button class="glide__bullet" data-glide-dir="=1"></button>
        <button class="glide__bullet" data-glide-dir="=2"></button>
        <button class="glide__bullet" data-glide-dir="=3"></button>
        <button class="glide__bullet" data-glide-dir="=4"></button>
      </div>
    </div>
    <div class="glide__arrows" data-glide-el="controls">
      <button class="glide__arrow glide__arrow--left" data-glide-dir="<">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M15 6L9 12L15 18M15 12H15.01"
              :stroke=fontColorSecondary
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            ></path>
          </g>
        </svg>
      </button>
      <button class="glide__arrow glide__arrow--right" data-glide-dir=">">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M9 6L15 12L9 18M9 12H9.01"
              :stroke=fontColorSecondary
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            ></path>
          </g>
        </svg>
      </button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '@glidejs/glide/dist/css/glide.core.min.css';

.glide {
  height: 100%;

  .glide__track {
    height: 100%;

    .glide__slides {
      position: relative;
      height: 100%;

      .glide__slide {
        padding: 0 var(--spacing-xl);

        @media (min-width: 768px) {
          padding: 0 var(--spacing-xxl);
        }
      }
    }

    .glide__bullets {
      position: absolute;
      bottom: 10%;
      left: 50%;
      transform: translateX(-50%);
      width: 60%;
      display: flex;
      justify-content: space-between;

      @media (min-width: 768px) {
        bottom: 25%;
        width: 25%;
      }

      .glide__bullet {
        // TODO: add tokens for 20 and 24px spacing
        width: 20px;
        height: 20px;
        border-radius: 50%;
        padding: 0;
        border: 0;
        background-color: var(--font-color-primary);

        @media (min-width: 768px) {
          width: 24px;
          height: 24px;
        }

        &.glide__bullet--active {
          background-color: var(--font-color-secondary);
        }

        &:hover {
          transition: background-color 0.3s ease-in-out;
          background-color: var(--font-color-secondary);
          cursor: pointer;
        }
      }
    }
  }

  .glide__arrows {
    .glide__arrow {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: var(--spacing-xl);
      height: var(--spacing-xl);

      @media (min-width: 768px) {
        width: var(--spacing-xxl);
        height: var(--spacing-xxl);
      }

      &.glide__arrow--left {
        left: 0;
      }

      &.glide__arrow--right {
        right: 0;
      }

      &:hover {
        cursor: pointer;
      }

      // deactivates default button styles
      background-color: transparent;
      box-shadow: initial;
      border: none;
      outline: none;

      svg {
        max-height: 100%;
        max-width: 100%;
      }
    }
  }
}
</style>
