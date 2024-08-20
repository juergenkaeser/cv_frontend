<script setup lang="ts">
  import Navigation from './components/StickyNavigation.vue'
  import Profile from './components/MyProfile.vue'
  import CurriculumVitae from './components/CurriculumVitae.vue';
  import ProjectList from './components/ProjectList.vue'
  import { ref } from 'vue'

  const me = ref()
  const cv = ref()
  const projects = ref()

  function naviClick(e: Element) {
    e.scrollIntoView({ behavior: "smooth" });
  };
</script>

<template>
  <main>
    <Navigation
      @navi-0-click="naviClick(me)"
      @navi-1-click="naviClick(cv)"
      @navi-2-click="naviClick(projects)"
    />
    <div class="profile" ref="me">
      <Profile />
    </div>
    <div class="cv" ref="cv">
      <CurriculumVitae />
    </div>
    <div class="projects" ref="projects">
      <ProjectList />
    </div>
    
    <!-- TODO: Make me work!    
    <div class="glide">
      <div class="glide__track" data-glide-el="track">
        <ul class="glide__slides">
          <li class="glide__slide">0</li>
          <li class="glide__slide">1</li>
          <li class="glide__slide">2</li>
        </ul>
      </div>
      <div class="glide__arrows" data-glide-el="controls">
        <button class="glide__arrow glide__arrow--left" data-glide-dir="<">prev</button>
        <button class="glide__arrow glide__arrow--right" data-glide-dir=">">next</button>
      </div>
    </div> -->

  </main>
</template>

<style lang="scss">
  :root {
    --bg-color: #1a1a1a;
    --font-color-primary: #ffffff84;
    --font-color-secondary: #29cac2b1;
    --font-size-1: 16px;
    --font-size-2: 20px;
    --font-size-3: 24px;
    --spacing-small: 4px;
    --spacing-medium: 8px;
    --spacing-large: 16px;
    --navi-padding: 40px;
  }

  #app {
    display: block;
    width: 100%;
  }
 
  body,
  #app {
    margin: 0;
    background-color: var(--bg-color);
    color: var(--font-color-primary);
  }

  .profile,
  .cv,
  .projects {
    padding-top: var(--navi-padding);
    height: 100vh;
  }
 
  ul {
    padding: 0;
    margin: var(--spacing-large) 0 0 0;

    &:before {
      content: attr(aria-label);
      font-size: 120%;
      font-weight: bold;
      font-style: italic;
      color: var(--font-color-secondary);
    }
  }
 
  li {
    list-style-type: none;
    margin-bottom: var(--spacing-small);
    padding-left: var(--spacing-medium);
  }
</style>
