<template>
  <ul class="navigation" ref="navigation" role="navigation">
    <li class="navigation-element" @click="this.$refs.first.scrollIntoView()">About me</li>
    <li class="navigation-element" @click="this.$refs.second.scrollIntoView()">Curriculum Vitae</li>
    <li class="navigation-element" @click="this.$refs.third.scrollIntoView()">Projects</li>
  </ul>
  <div class="scroll-element" ref="first">1</div>
  <div class="scroll-element" ref="second">2</div>
  <div class="scroll-element" ref="third">3</div>
</template>
 
<style>
  .navigation {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 99;
    background-color: #74b5ba;
    display: flex;
    justify-content: space-between;
    width: calc(100% - 64px);
    margin: 4px 32px;
    padding-inline-start: 0;
    list-style-type: none;
    border-radius: 4px;
  }
 
  .navigation-element {
    width: calc(100% / 3);
    text-align: center;
    background-color: inherit;
    border-radius: 4px;
    transition: background-color 200ms ease-in-out;
    margin-bottom: 0;
    padding-left: 0;
  }
 
  .navigation-element:hover {
    cursor: pointer;
    background-color: #18838c;
  }
 
  .scroll-element {
    background-color: grey;
    height: 100vh;
    line-height: 100vh;
    vertical-align: center;
    text-align: center;
    font-size: 32px;
  }
 
  .scroll-element:nth-child(even) {
    background-color: lightgrey;
  }
</style>