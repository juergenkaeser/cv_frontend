<script setup lang="ts">
  import Navigation from './components/StickyNavigation.vue'
  import Profile from './components/MyProfile.vue'
  import CurriculumVitae from './components/CurriculumVitae.vue';
  import ProjectList from './components/ProjectList.vue'
  import Impressum from './components/MyImpressum.vue'
  import { ref } from 'vue'

  const me = ref()
  const cv = ref()
  const projects = ref()
  const impressumHidden = ref(true)

  /* TODO: Make me work for A11Y
  const showImpressumBtn = ref()
  onMounted(() => {
    showImpressumBtn.value.addEventListener('keydown', function(event) {
      if (event.keyCode === 'ENTER' || event.keyCode === 'SPACE') {
          event.preventDefault(); // Prevents unintentional form submissions, page scrollings, the like
          showImpressum();
      }
    });
  }) */

  function naviClick(e: Element) {
    e.scrollIntoView({ behavior: "smooth" });
  };

  function showImpressum() {
    impressumHidden.value = false
    let element = document.getElementById("app");
    if (element) {
      element.scrollIntoView();
    }
  }

  function hideImpressum() {
    impressumHidden.value = true
  }
</script>

<template>
  <main>
    <div class="content-wrapper" v-if="impressumHidden">
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
      <div class="show-impressum" tabindex="0" ref="showImpressumBtn" role="button" @click="showImpressum()">Impressum</div>
    </div>
    <div class="impressum" ref="impressum" v-else>
      <Impressum @hide-impressum="hideImpressum()"/>
    </div>
  </main>
</template>

<style lang="scss">
  :root {
    // TODO: Make breakpoint work in media-querys
    --breakpoint-desktop: 768px;
    --bg-color: #1a1a1a;
    --font-color-primary: #ffffff84;
    --font-color-secondary: #29cac2b1;
    --font-size-1: 16px;
    --font-size-2: 20px;
    --font-size-3: 24px;
    --spacing-s: 4px;
    --spacing-m: 8px;
    --spacing-l: 16px;
    --spacing-xl: 40px;
    --spacing-xxl: 80px;
    --navi-height-mobile: 28px;
    --navi-height-desktop: 40px;
    --font-size-navi-mobile: 12px;
    --font-size-navi-desktop: 16px;
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
    padding-top: var(--navi-height-mobile);

    @media (min-width: 768px) {
      padding-top: var(--navi-height-desktop);
    }
  }

  .profile {
    height: 100vh;
  }

  .cv,
  .projects {
    @media (min-width: 768px) {
      height: 100vh;
    }
  }

  .show-impressum {
    margin: 0 auto;
    width: fit-content;

    &:hover {
      cursor: pointer;
    }
  }

  .impressum {
    padding-top: var(--navi-height-mobile);

    @media (min-width: var(--breakpoint-desktop)) {
      padding-top: var(--navi-height-desktop);
    }
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
    margin-bottom: var(--spacing-s);
    padding-left: var(--spacing-m);
  }
</style>
