<script setup lang="ts">
  import ProjectItem from './ProjectItem.vue'
  import { onMounted } from 'vue'
  import Glide, { Controls } from '@glidejs/glide/dist/glide.modular.esm'

  onMounted(() => {
    new Glide('.glide', {
      type: 'carousel'
    }
    ).mount({ Controls })
  })
</script>

<template>
  <div class="glide">
    <div class="glide__track" data-glide-el="track">
      <ul class="glide__slides">
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>Service Funnel Frontend</template>
            <template #subline><a href="https://www.o2online.de/service/" target="_blank">Telefónica Germany GmbH & Co. OHG</a></template>
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>Building Frontend Components for a CMS</template>
            <template #subline><a href="https://www.o2online.de/" target="_blank">Telefónica Germany GmbH & Co. OHG</a></template>
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>This very page</template>
            <template #subline>Subline</template>
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
          </ProjectItem>
        </li>
      </ul>
    </div>
    <div class="glide__arrows" data-glide-el="controls">
      <button class="glide__arrow glide__arrow--left" data-glide-dir="<">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <path d="M15 6L9 12L15 18M15 12H15.01" stroke="#29cac2b1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path> </g></svg>
      </button>
      <button class="glide__arrow glide__arrow--right" data-glide-dir=">">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <path d="M9 6L15 12L9 18M9 12H9.01" stroke="#29cac2b1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path> </g></svg>
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
          padding: 0 120px;
        }
      }
    }

    .glide__arrows {
      .glide__arrow {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        width: 80px;
        height: 80px;
        color: white;

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