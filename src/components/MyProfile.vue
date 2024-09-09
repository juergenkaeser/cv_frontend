<script setup>
import { defineProps } from 'vue'
import data from '../assets/data.json'

defineProps({
  fontColorSecondary: {
    type: String,
    default: '',
    required: true
  }
})
</script>

<template>
  <div class="background-container">
    <h1 class="profile__title">Portfolio von {{ data.firstName }} {{ data.lastName }}</h1>
    <h2 class="profile__title">Über mich</h2>
    <h3 class="profile__name">{{ data.firstName }} {{ data.lastName }}</h3>
    <p class="profile__profession">{{ data.jobDescription }} aus {{ data.city }}</p>
    <div class="profile__description-wrapper">
      <p class="profile__description-item">
        {{ data.descriptionText.text1 }}
      </p>
      <p class="profile__description-item">
        {{ data.descriptionText.text2 }}
      </p>
      <p class="profile__description-item">
        {{ data.descriptionText.text3 }}
      </p>
    </div>
    <h4>Weitere Profile und Kontakt:</h4>
    <div class="links">
      <br />
      <a href="https://github.com/juergenkaeser" target="_blank">
        <svg width="98" height="96" xmlns="http://www.w3.org/2000/svg">
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M48.854 0C21.839 0 0 22 0 49.217c0 21.756 13.993 40.172 33.405 46.69 2.427.49 3.316-1.059 3.316-2.362 0-1.141-.08-5.052-.08-9.127-13.59 2.934-16.42-5.867-16.42-5.867-2.184-5.704-5.42-7.17-5.42-7.17-4.448-3.015.324-3.015.324-3.015 4.934.326 7.523 5.052 7.523 5.052 4.367 7.496 11.404 5.378 14.235 4.074.404-3.178 1.699-5.378 3.074-6.6-10.839-1.141-22.243-5.378-22.243-24.283 0-5.378 1.94-9.778 5.014-13.2-.485-1.222-2.184-6.275.486-13.038 0 0 4.125-1.304 13.426 5.052a46.97 46.97 0 0 1 12.214-1.63c4.125 0 8.33.571 12.213 1.63 9.302-6.356 13.427-5.052 13.427-5.052 2.67 6.763.97 11.816.485 13.038 3.155 3.422 5.015 7.822 5.015 13.2 0 18.905-11.404 23.06-22.324 24.283 1.78 1.548 3.316 4.481 3.316 9.126 0 6.6-.08 11.897-.08 13.526 0 1.304.89 2.853 3.316 2.364 19.412-6.52 33.405-24.935 33.405-46.691C97.707 22 75.788 0 48.854 0z"
            :fill="fontColorSecondary"
          />
        </svg>
      </a>
      <a href="https://www.linkedin.com/in/juergen-kaeser/" target="_blank">
        <svg
          width="98"
          height="98"
          viewBox="0 0 256 256"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          preserveAspectRatio="xMidYMid"
        >
          <g>
            <path
              d="M218.123122,218.127392 L180.191928,218.127392 L180.191928,158.724263 C180.191928,144.559023 179.939053,126.323993 160.463756,126.323993 C140.707926,126.323993 137.685284,141.757585 137.685284,157.692986 L137.685284,218.123441 L99.7540894,218.123441 L99.7540894,95.9665207 L136.168036,95.9665207 L136.168036,112.660562 L136.677736,112.660562 C144.102746,99.9650027 157.908637,92.3824528 172.605689,92.9280076 C211.050535,92.9280076 218.138927,118.216023 218.138927,151.114151 L218.123122,218.127392 Z M56.9550587,79.2685282 C44.7981969,79.2707099 34.9413443,69.4171797 34.9391618,57.260052 C34.93698,45.1029244 44.7902948,35.2458562 56.9471566,35.2436736 C69.1040185,35.2414916 78.9608713,45.0950217 78.963054,57.2521493 C78.9641017,63.090208 76.6459976,68.6895714 72.5186979,72.8184433 C68.3913982,76.9473153 62.7929898,79.26748 56.9550587,79.2685282 M75.9206558,218.127392 L37.94995,218.127392 L37.94995,95.9665207 L75.9206558,95.9665207 L75.9206558,218.127392 Z M237.033403,0.0182577091 L18.8895249,0.0182577091 C8.57959469,-0.0980923971 0.124827038,8.16056231 -0.001,18.4706066 L-0.001,237.524091 C0.120519052,247.839103 8.57460631,256.105934 18.8895249,255.9977 L237.033403,255.9977 C247.368728,256.125818 255.855922,247.859464 255.999,237.524091 L255.999,18.4548016 C255.851624,8.12438979 247.363742,-0.133792868 237.033403,0.000790807055"
              :fill="fontColorSecondary"
            ></path>
          </g>
        </svg>
      </a>
      <a href="https://www.xing.com/profile/Juergen_Kaeser6" target="_blank">
        <svg
          :fill="fontColorSecondary"
          version="1.1"
          id="Capa_1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          width="98"
          height="98"
          viewBox="0 0 540.543 540.543"
          xml:space="preserve"
        >
          <g>
            <g>
              <path
                d="M129.989,378.772c8.274,0,15.361-5.006,21.243-15.036c53.813-95.423,81.806-145.093,83.991-149.028l-53.593-93.458    c-5.667-9.804-12.858-14.707-21.567-14.707H81.953c-5.019,0-8.495,1.634-10.459,4.902c-2.399,3.268-2.289,7.301,0.325,12.087    l52.613,91.176c0.214,0.232,0.214,0.331,0,0.331L41.75,361.453c-2.172,4.149-2.172,8.066,0,11.757    c2.173,3.715,5.557,5.562,10.129,5.562H129.989z"
              />
              <path
                d="M488.492,0h-78.758c-8.495,0-15.472,4.902-20.912,14.707C277.053,212.97,219.206,315.596,215.283,322.555l110.784,203.282    c5.227,9.804,12.418,14.706,21.567,14.706h78.104c4.791,0,8.28-1.634,10.459-4.902c2.172-3.715,2.068-7.748-0.325-12.099    L326.073,322.555v-0.318L498.627,16.995c2.393-4.571,2.393-8.592,0-12.087C496.662,1.634,493.284,0,488.492,0z"
              />
            </g>
          </g>
        </svg>
      </a>
    </div>
  </div>
</template>

<style lang="scss">
.background-container {
  position: relative;
  background: rgba(0, 0, 0, 0.8) url('../assets/lake-view.JPG');
  background-blend-mode: darken;
  background-position: center;
  background-size: cover;
  min-height: calc(100vh - var(--navi-height-mobile));
  padding: var(--spacing-l);

  @media (max-width: 768px) {
    background: transparent;
    min-height: calc(100vh - var(--navi-height-desktop));
  }

  @media (min-width: 768px) {
    padding: var(--spacing-l) var(--spacing-l) var(--spacing-xxl) var(--spacing-l);
  }

  .profile__profession {
    font-style: italic;
    font-weight: bold;
  }

  .profile__name,
  .profile__profession {
    margin-block-start: 0;
    margin-block-end: 0;
  }

  .profile__profession,
  .profile__description-wrapper {
    margin-top: var(--spacing-m);
  }

  .profile__description-wrapper {
    max-width: 100%;

    @media (min-width: 768px) {
      max-width: 50%;
    }

    @media (min-width: 1200px) {
      max-width: 30%;
    }
  }

  .profile__description-item {
    margin-bottom: var(--spacing-l);
  }

  h4 {
    margin-top: var(--spacing-m);
    font-weight: bold;
  }

  .links {
    margin-top: var(--spacing-m);

    @media (min-width: 768px) {
      margin-top: var(--spacing-l);
    }

    a {
      &:not(:last-child) {
        margin-right: var(--spacing-m);

        @media (min-width: 768px) {
          margin-right: var(--spacing-l);
        }
      }

      &:hover {
        background-color: transparent;
      }
    }
  }
}
</style>
