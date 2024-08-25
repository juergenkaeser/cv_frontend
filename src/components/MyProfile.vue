<script setup>
import { defineProps } from 'vue';

defineProps({
  fontColorSecondary: {
    type: String,
    default: '',
    required: true
  }
});
</script>

<template>
  <div class="background-container">
    <h1 class="profile__name">Jürgen Käser</h1>
    <p class="profile__profession">Softwaredeveloper</p>
    <div class="profile__description-wrapper">
      <p class="profile__description-item">
        Thank you for visiting my website, which I created using the JavaScript framework Vue.js.
      </p>
      <p class="profile__description-item">
        After completing my degree in business administration I found my love for programming.
      Since then I have already gained several years of professional experience and am currently in the process
      of retraining as an Computer Science Expert - Subject Area: Software Development (IHK) at Control Data Training GmbH in Nuremberg. For the end of February next
      year, I am looking for an internship in software development and am also interested in a
      permanent position beyond that.
      </p>
      <p class="profile__description-item">
        Here you will find an overview of my working experience and some of my projects. Enjoy!
      </p>
    </div>
    <div class="github">
      <p>Visit me on GitHub:</p>
      <br />
      <a href="https://github.com/juergenkaeser" target="_blank">
        <svg width="98" height="96" xmlns="http://www.w3.org/2000/svg">
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M48.854 0C21.839 0 0 22 0 49.217c0 21.756 13.993 40.172 33.405 46.69 2.427.49 3.316-1.059 3.316-2.362 0-1.141-.08-5.052-.08-9.127-13.59 2.934-16.42-5.867-16.42-5.867-2.184-5.704-5.42-7.17-5.42-7.17-4.448-3.015.324-3.015.324-3.015 4.934.326 7.523 5.052 7.523 5.052 4.367 7.496 11.404 5.378 14.235 4.074.404-3.178 1.699-5.378 3.074-6.6-10.839-1.141-22.243-5.378-22.243-24.283 0-5.378 1.94-9.778 5.014-13.2-.485-1.222-2.184-6.275.486-13.038 0 0 4.125-1.304 13.426 5.052a46.97 46.97 0 0 1 12.214-1.63c4.125 0 8.33.571 12.213 1.63 9.302-6.356 13.427-5.052 13.427-5.052 2.67 6.763.97 11.816.485 13.038 3.155 3.422 5.015 7.822 5.015 13.2 0 18.905-11.404 23.06-22.324 24.283 1.78 1.548 3.316 4.481 3.316 9.126 0 6.6-.08 11.897-.08 13.526 0 1.304.89 2.853 3.316 2.364 19.412-6.52 33.405-24.935 33.405-46.691C97.707 22 75.788 0 48.854 0z"
            :fill=fontColorSecondary
          />
        </svg>
      </a>
    </div>
  </div>
</template>

<style lang="scss">
.background-container {
  position: relative;
  background: rgba(0, 0, 0, 0.7) url('../assets/persons_shadow.JPG');
  background-blend-mode: darken;
  background-position: center;
  background-size: cover;
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
  }

  .profile__name {
    color: var(--font-color-secondary);
    font-weight: bold;
  }

  .profile__profession,
  .profile__description-wrapper {
    margin-top: var(--spacing-m);
  }

  .profile__description-wrapper {
    max-width: 100%;

    @media (min-width: 768px) {
      max-width: 40%;
    }
  }

  .profile__description-item {
    margin-bottom: var(--spacing-l);
  }

  .github {
    position: absolute;
    bottom: 0;
    margin-top: var(--spacing-xl);
    padding-bottom: var(--spacing-s);

    @media (min-width: 768px) {
      padding-bottom: var(--spacing-s);
    }

    a:hover {
      background-color: transparent;
    }

    p {
      opacity: 0;

      @media (min-width: 768px) {
        opacity: 1;
      }
    }
  }
}
</style>
