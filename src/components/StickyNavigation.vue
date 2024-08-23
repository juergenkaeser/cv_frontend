<template>
  <ul class="navigation" ref="navigation" role="navigation">
    <li class="navigation-element" @click="$emit('navi-0-click')">About me</li>
    <li class="navigation-element" @click="$emit('navi-1-click')">Curriculum Vitae</li>
    <li class="navigation-element" @click="$emit('navi-2-click')">Projects</li>
  </ul>
</template>
 
<style lang="scss">
  .navigation {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 99;
    background-color: var(--font-color-secondary);
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
    color: white;
    font-weight: bold;
    user-select: none;
    font-size: var(--font-size-navi-mobile);
    padding: var(--spacing-s);

    @media (min-width: 768px) {
      font-size: var(--font-size-navi-desktop);
      padding: var(--spacing-m);
    }

    &:nth-child(2) {
      border-left: 1px solid var(--font-color-primary);
      border-right: 1px solid var(--font-color-primary);
    }
  }
 
  .navigation-element:hover {
    cursor: pointer;
    background-color: #18838c;
  }
</style>