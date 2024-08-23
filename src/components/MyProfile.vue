<template>
  <div class="background-container">
    <h2 class="profile__name">Jürgen Käser</h2>
    <p class="profile__profession">Software Engineer</p>
    <p class="profile__description">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
  </div>
</template>

<style lang="scss">
  .background-container {
    background-image: url(https://placehold.co/1920x1080/31343C/EEE);
    background-position: center;
    height: 100%;
    padding: var(--spacing-s);

    @media (min-width: 786px) {
      padding: var(--spacing-l);
    }

    .profile__name,
    .profile__profession {
      margin-block-start: 0;
      margin-block-end: 0;
      font-style: italic;
    }

    .profile__name {
      color: var(--font-color-secondary);
      font-weight: bold;
      font-size: 32px;
    }
  
    .profile__profession,
    .profile__description {
      margin-top: var(--spacing-m);
    }

    .profile__description {
      @media (min-width: 786px) {
        max-width:50%;
      }
    }
  }
</style>