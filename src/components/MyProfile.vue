<template>
  <div class="background-container">
    <h2 class="profile__name">Jürgen Käser</h2>
    <p class="profile__profession">Softwaredeveloper</p>
    <p class="profile__description">Thank you for visiting my website. Here you will find an overview of my working experience and some of my projects </p>
  </div>
</template>

<style lang="scss">
  .background-container {
    background-image: url(https://placehold.co/1920x1080/31343C/EEE);
    background-position: center;
    height: 100%;
    padding: var(--spacing-s);

    @media (min-width: 768px) {
      padding: var(--spacing-l);
    }

    .profile__name,
    .profile__profession {
      margin-block-start: 0;
      margin-block-end: 0;
    }

    .profile__profession {
      font-style: italic;
      font-weight: bold;
      font-size: 120%;
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
      @media (min-width: 768px) {
        max-width:50%;
      }
    }
  }
</style>