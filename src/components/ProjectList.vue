<script setup lang="ts">
  import ProjectItem from './ProjectItem.vue'
  import { onMounted } from 'vue'
  import Glide from '@glidejs/glide'

  onMounted(() => {
    new Glide('.glide').mount()
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
      <button class="glide__arrow glide__arrow--left" data-glide-dir="<">prev</button>
      <button class="glide__arrow glide__arrow--right" data-glide-dir=">">next</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  @import '@glidejs/glide/dist/css/glide.core.min.css';

  .glide {
    height: 100%;

    .glide__track {
      height: 90%;

      .glide__slides {
        height: 100%;
      }
    }

    .glide__arrows {
      text-align: center;
    }
  }
</style>