<template>
  <div class="project-item">
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
</template>

<style lang="scss">
  .project-item {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;

    a {
      border-radius: var(--spacing-s);
    }
  }

  .project-item__headline,
  .project-item__subline {
    color: var(--font-color-secondary);
  }

  .project-item__headline {
    font-weight: bold;
  }
 
  .project-item__subline {
    margin-top: var(--spacing-s);
    font-style: italic;
  }

  .project-item__content {
    margin-top: var(--spacing-m);
    font-size: 100%;
  }
</style>
