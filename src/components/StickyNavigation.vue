<script setup>
import { ref, onMounted, watch } from 'vue';
const props = defineProps({
  activeComponent: {
    type: String,
    required: true
  }
});

// TODO: change other emits like that
const emit = defineEmits(['navi-0-click', 'navi-1-click', 'navi-2-click'])
const naviElement0 = ref()
const naviElement1 = ref()
const naviElement2 = ref()

onMounted(() => {
  watch(() => props.activeComponent, (newValue) => {
    removeActiveClass()
    if (newValue === 'profile') {
      document.getElementsByClassName("navigation-element")[0].classList.add("active")
    } else if (newValue === 'cv') {
      document.getElementsByClassName("navigation-element")[1].classList.add("active")
    } else if (newValue === 'projects') {
      document.getElementsByClassName("navigation-element")[2].classList.add("active")
    }
 });
})

function setActiveClick(e, eventName) {
  removeActiveClass()
  addActiveClass(e)
  emit(eventName)
}

function addActiveClass(e) {
  e.classList.add('active')
}

function removeActiveClass() {
  const el = document.getElementsByClassName('active')[0]
  el.classList.remove('active')
}
</script>

<template>
  <ul class="navigation" ref="navigation" role="navigation">
    <li
      class="navigation-element active"
      ref="naviElement0"
      @click="setActiveClick(naviElement0, 'navi-0-click')"
    >
      <p>Über mich</p>
    </li>
    <li
      class="navigation-element"
      ref="naviElement1"
      @click="setActiveClick(naviElement1, 'navi-1-click')"
    >
      <p>Curriculum Vitae</p>
    </li>
    <li
      class="navigation-element"
      ref="naviElement2"
      @click="setActiveClick(naviElement2, 'navi-2-click')"
    >
      <p>Projekte</p>
    </li>
  </ul>
</template>

<style lang="scss">
.navigation {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 99;
  background-color: var(--font-color-secondary-dark);
  display: flex;
  width: 100%;
  padding-inline-start: 0;
  list-style-type: none;
  height: var(--navi-height-mobile);

  @media (min-width: 768px) {
    height: var(--navi-height-desktop);
  }
}

.navigation-element {
  width: calc(100% / 3);
  text-align: center;
  background-color: inherit;
  transition: background-color 200ms ease-in-out;
  margin-bottom: 0;
  color: var(--font-color-primary);
  font-size: 100%;
  font-weight: bold;
  user-select: none;
  padding: var(--spacing-s) 0;

  @media (min-width: 768px) {
    padding: 6px;
  }

  &:nth-child(2) {
    border-left: 1px solid var(--font-color-primary);
    border-right: 1px solid var(--font-color-primary);
  }

  &.active {
    background-color: var(--font-color-secondary);
  }

  &:hover {
    cursor: pointer;
    background-color: var(--font-color-secondary);
  }

  p {
    font-weight: inherit;
  }
}
</style>
