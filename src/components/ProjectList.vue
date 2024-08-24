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
            <template #subline>Industry: Telecommunications</template>
            Development of a microapp with the frontend framework Vue.js for a large german telecommunications company. The application enables users to quickly find help on the company's website and thereby save service costs. The application is highly animated and was implemented down to the smallest detail and in close coordination with the customer.
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>Building Frontend Components for a Content Management System</template>
            <template #subline>Industry: Telecommunications</template>
              Development of frontend components for a large german telecommunications company. As part of an agile team, I worked as a frontend developer. The components were built with the web component framework Lit, JavaScript/TypeScript, HTML and CSS/SCSS. I customized the components exactly to the customer's wishes and highly animated some of them with CSS.
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>Automated user interface tests of a tourism software</template>
            <template #subline>Industry: Travel / Softwaredevelopment</template>
            For an in-house software of a software developer who specializes in solutions in the tourism environment, I created automated user interface tests using the test software QF-Test and also wrote scripts in Groovy.
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>Maintainence and testing of inhouse-software</template>
            <template #subline>Industry: Public Service / Softwaredevelopment</template>
            Development of automated unit tests for an existing in-house software in C#. Additionally, I fixed bugs in the software reported by customers.
          </ProjectItem>
        </li>
        <li class="glide__slide">
          <ProjectItem>
            <template #headline>This very website</template>
            <template #subline>Home project</template>
              <p>This page was built with the frontend framework Vue.js using the new thirth version of the framework.</p>
              <br />
              <a href="https://github.com/juergenkaeser/cv_frontend" target="_blank">Project on GitHub</a>
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
          padding: 0 var(--spacing-xl);

          @media (min-width: 768px) {
            padding: 0 var(--spacing-xxl);
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