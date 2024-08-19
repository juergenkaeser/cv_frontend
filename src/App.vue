<script setup lang="ts">
  import ProjectNavigation from './components/ProjectNavigation.vue'
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
    <ProjectNavigation
    @navi-0-click="naviClick(me)"
    @navi-1-click="naviClick(cv)"
    @navi-2-click="naviClick(projects)"
    />
    <div class="profile" ref="me">
      <h2 class="profile__name">Jürgen Käser</h2>
      <p class="profile__profession">Software Engineer</p>
      <div class="cv-lists">
        <ul class="cv-list" aria-label="Professional experience">
          <li class="cv-list-item">Software Engineer - arsmedium AG (2 years, 4 months)</li>
          <li class="cv-list-item">Softwaretester / -developer - ISO Travel Solutions GmbH (1 year, 3 months)</li>
          <li class="cv-list-item">Intern Software Engineering - mediendesign AG (6 months)</li>
          <li class="cv-list-item">Working Student IT - Siemens AG - Digital Factory Division (1 year, 3 months)</li>
        </ul>
        <ul class="cv-list" aria-label="Education">
          <li class="cv-list-item">Expected early 2026: Computer Science Expert - Subject Area: Software Development (IHK)</li>
          <li class="cv-list-item">Bachelor of arts: Business administration (Nuremberg Institute of technology)</li>
        </ul>
        <ul class="cv-list" aria-label="Technologies">
          <li class="cv-list-item">Java</li>
          <li class="cv-list-item">SQL</li>
          <li class="cv-list-item">JavaScript / TypeScript</li>
          <li class="cv-list-item">CSS / SCSS</li>
          <li class="cv-list-item">HTML</li>
          <li class="cv-list-item">Vue.js</li>
        </ul>
      </div>
    </div>
    <div class="cv" ref="cv">
      CV Test
    </div>
    <div class="project-slider" ref="projects">
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

  .profile {
    padding-top: var(--navi-padding);
  }
 
  .profile__name,
  .profile__profession {
    margin-block-start: 0;
    margin-block-end: 0;
  }

  .profile__name {
    color: var(--font-color-secondary);
    font-weight: bold;
  }
 
  .profile__profession {
    margin-top: var(--spacing-medium);
    font-style: italic;
  }

  .cv {
    background-color: grey;
    height: 100vh;
    line-height: 100vh;
    vertical-align: center;
    text-align: center;
    font-size: 32px;
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
