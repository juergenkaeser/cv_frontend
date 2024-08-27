
<script setup>
import data from '../assets/data.json';
</script>

<template>
    <div class="cv-lists">
      <h2 class="cv-list-headline" role="label">{{ data.experiencesHeadline }}</h2>
      <ul class="cv-list">
        <li class="cv-list-item"><span class="profession">{{ data.experiences[0].job }}</span> - {{ data.experiences[0].entry }}</li>
        <li class="cv-list-item"><span class="profession">{{ data.experiences[1].job }}</span> - {{ data.experiences[1].entry }}</li>
        <li class="cv-list-item"><span class="profession">{{ data.experiences[2].job }}</span> - {{ data.experiences[2].entry }}</li>
        <li class="cv-list-item"><span class="profession">{{ data.experiences[3].job }}</span> - {{ data.experiences[3].entry }}</li>
      </ul>
      <h2 class="cv-list-headline" role="label">{{ data.educationHeadline }}</h2>
      <ul class="cv-list" aria-label="Education">
        <li class="cv-list-item">{{ data.degrees.degree1 }}</li>
        <li class="cv-list-item">{{ data.degrees.degree2 }}</li>
      </ul>
      <h2 class="cv-list-headline" role="label">{{ data.technologiesHeadline }}</h2>
      <ul class="cv-list">
        <li class="cv-list-item">{{ data.techologies.tech1 }}</li>
        <li class="cv-list-item">{{ data.techologies.tech2 }}</li>
        <li class="cv-list-item">{{ data.techologies.tech3 }}</li>
        <li class="cv-list-item">{{ data.techologies.tech4 }}</li>
        <li class="cv-list-item">{{ data.techologies.tech5 }}</li>
        <li class="cv-list-item">{{ data.techologies.tech6 }}</li>
      </ul>
    </div>
</template>

<style lang="scss">
  .cv-lists {
    max-height: 100%;
    height: 100%;
    padding: var(--spacing-s);

    @media (min-width: 768px) {
      padding: var(--spacing-l);
    }

    .cv-list {
      padding: 0; 
      margin: var(--spacing-large) 0 0 0;
    }

    .cv-list-item {
      .profession {
        font-style: italic;
      }
    }
  }
</style>