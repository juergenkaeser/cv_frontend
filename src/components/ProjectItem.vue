<template>
  <div class="project-item">
    <div class="details">
      <h3 class="project-item__headline">
        <slot name="headline"></slot>
      </h3>
      <h4 class="project-item__subline">
        <slot name="subline"></slot>
      </h4>
      <p class="project-item__content">
        <slot></slot>
      </p>
    </div>
  </div>
</template>

<style lang="scss">
  .project-item__headline,
  .project-item__subline {
    color: var(--font-color-secondary);
  }

  .project-item__headline {
    font-weight: bold;
  }
 
  .project-item__subline {
    margin-top: var(--spacing-small);
    font-style: italic;
  }
</style>
