<template>
    <div class="cv-lists">
      <!-- TODO: better without before? -->
      <ul class="cv-list" aria-label="Professional experience">
        <li class="cv-list-item"><span class="profession">Software Engineer</span> - arsmedium AG (2 years, 4 months)</li>
        <li class="cv-list-item"><span class="profession">Softwaretester / -developer</span> - ISO Travel Solutions GmbH (1 year, 3 months)</li>
        <li class="cv-list-item"><span class="profession">Intern Software Engineering</span> - mediendesign AG (6 months)</li>
        <li class="cv-list-item"><span class="profession">Working Student IT</span> - Siemens AG - Digital Factory Division (1 year, 3 months)</li>
      </ul>
      <ul class="cv-list" aria-label="Education">
        <li class="cv-list-item">Expected early 2026: Computer Science Expert - Subject Area: Software Development (IHK)</li>
        <li class="cv-list-item">Bachelor of arts: Business administration (Nuremberg Institute of technology)</li>
      </ul>
      <ul class="cv-list" aria-label="Technologies">
        <li class="cv-list-item">Java</li>
        <li class="cv-list-item">SQL</li>
        <li class="cv-list-item">JavaScript / TypeScript</li>
        <li class="cv-list-item">CSS / SCSS</li>
        <li class="cv-list-item">HTML</li>
        <li class="cv-list-item">Vue.js</li>
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

    .cv-list-item {
      .profession {
        font-style: italic;
      }
    }
  }
</style>