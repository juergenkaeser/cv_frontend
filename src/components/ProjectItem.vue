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

<style scoped>
  .details {
    color: rgba(208, 105, 20, 0.678);
  }
</style>
