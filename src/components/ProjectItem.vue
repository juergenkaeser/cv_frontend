<template>
  <div class="item">
    <div class="details">
      <h3>
        <slot name="heading"></slot>
      </h3>
      <slot></slot>
    </div>
  </div>
</template>

<style lang="scss">
  .details {
    h3 {
      color: var(--font-color-secondary);
      font-weight: bold;
    }
  }
</style>
