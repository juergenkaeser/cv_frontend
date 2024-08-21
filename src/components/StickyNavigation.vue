<template>
  <ul class="navigation" ref="navigation" role="navigation">
    <li class="navigation-element" @click="$emit('navi-0-click')">About me</li>
    <li class="navigation-element" @click="$emit('navi-1-click')">Curriculum Vitae</li>
    <li class="navigation-element" @click="$emit('navi-2-click')">Projects</li>
  </ul>
</template>
 
<style>
  .navigation {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 99;
    background-color: var(--font-color-secondary);
    display: flex;
    justify-content: space-between;
    width: calc(100% - 64px);
    margin: var(--spacing-s) 32px;
    padding-inline-start: 0;
    list-style-type: none;
    border-radius: var(--spacing-s);
  }
 
  .navigation-element {
    width: calc(100% / 3);
    text-align: center;
    background-color: inherit;
    border-radius: var(--spacing-s);
    transition: background-color 200ms ease-in-out;
    margin-bottom: 0;
    padding-left: 0;
    color: white;
    font-weight: bold;
    user-select: none;
  }
 
  .navigation-element:hover {
    cursor: pointer;
    background-color: #18838c;
  }
</style>