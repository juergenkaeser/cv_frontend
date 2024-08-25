<script setup lang="ts">
import Navigation from './components/StickyNavigation.vue'
import Profile from './components/MyProfile.vue'
import CurriculumVitae from './components/CurriculumVitae.vue'
import ProjectList from './components/ProjectList.vue'
import Impressum from './components/MyImpressum.vue'
import { ref, onBeforeMount, onMounted } from 'vue'

let fontColorSecondary = ''
onBeforeMount(() => {
  fontColorSecondary = getComputedStyle(document.body).getPropertyValue('--font-color-secondary')
})

const me = ref()
const cv = ref()
const projects = ref()
const impressumHidden = ref(true)

let activeComponent = "";

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

onMounted(() => {
  observer.observe(me.value)
  observer.observe(cv.value)
  observer.observe(projects.value)
})

function naviClick(e: Element) {
  e.scrollIntoView({ behavior: 'smooth' })
}

function showImpressum() {
  impressumHidden.value = false
  let element = document.getElementById('app')
  if (element) {
    element.scrollIntoView()
  }
}

function hideImpressum() {
  impressumHidden.value = true
}

// Callback function triggered when visibility changes for each element
const callback = (entries: IntersectionObserverEntry[]) => {
  entries.forEach((entry) => {
    if (entry.intersectionRatio >= 0.6) {
      console.log(entry)
      activeComponent = entry.target.classList[0]
    }
  })
}

const observer = new IntersectionObserver(callback, {
  threshold: 0.6
})
</script>

<template>
  <main>
    <div class="content-wrapper" v-if="impressumHidden">
      <Navigation
        @navi-0-click="naviClick(me)"
        @navi-1-click="naviClick(cv)"
        @navi-2-click="naviClick(projects)"
        :activeComponent="activeComponent"
      />
      <div class="profile" ref="me">
        <Profile :fontColorSecondary="fontColorSecondary" />
      </div>
      <div class="cv" ref="cv">
        <CurriculumVitae />
      </div>
      <div class="projects" ref="projects">
        <ProjectList :fontColorSecondary="fontColorSecondary" />
      </div>
      <div
        class="impressum-btn"
        tabindex="0"
        ref="showImpressumBtn"
        role="button"
        @click="showImpressum()"
      >
        Impressum
      </div>
    </div>
    <div class="impressum" ref="impressum" v-else>
      <Impressum @hide-impressum="hideImpressum()" />
    </div>
  </main>
</template>

<style lang="scss">
:root {
  // TODO: Make breakpoint work in media-querys
  --breakpoint-desktop: 768px;
  --bg-color: #0c1618;
  --font-color-primary: #fffcee;
  --font-color-secondary: #5bb7a6;
  --font-color-secondary-dark: #453a49;
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

.profile,
.cv,
.projects {
  height: 100vh;
}

.impressum-btn {
  margin: 0 auto;
  margin-bottom: var(--spacing-s);
  width: fit-content;
  font-size: 120%;

  &:hover {
    cursor: pointer;
  }
}

.impressum {
  padding: var(--spacing-s);

  @media (min-width: 768px) {
    padding: var(--spacing-l);
  }
}

li {
  list-style-type: none;
  margin-bottom: var(--spacing-s);
  padding-left: var(--spacing-m);
}

li,
p {
  font-size: 90%;

  @media (min-width: 420px) {
    font-size: 100%;
  }

  @media (min-width: 768px) {
    font-size: 120%;
  }
}

a {
  color: var(--font-color-secondary);
  border-radius: var(--spacing-s);

  &:hover {
    background-color: var(--font-color-secondary-dark);
  }
}

h1,
h2,
h3 {
  color: var(--font-color-secondary);
  font-weight: bold;
}
</style>
