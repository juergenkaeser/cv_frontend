<template>
  <div class="background-container">
    <h2 class="profile__name">Jürgen Käser</h2>
    <p class="profile__profession">Software Engineer</p>
  </div>
</template>

<style lang="scss">
  .background-container {
    background-image: url(https://placehold.co/1920x1080/31343C/EEE);
    background-position: center;
    background-size: contain;
    height: 100%;

    .profile__name,
    .profile__profession {
      margin-block-start: 0;
      margin-block-end: 0;
    }

    .profile__name {
      color: var(--font-color-secondary);
      font-weight: bold;
    }
  
    .profile__profession {
      margin-top: var(--spacing-medium);
      font-style: italic;
    }
  }
</style>