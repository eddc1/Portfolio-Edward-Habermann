<template>
    <div id="home" class="header">
      <div class="container mx-auto header__container">
          <h5>Hello I&apos;m</h5>
          <h1>Edward Habermann</h1>
          <h5>Frontend Developer</h5>
        <CTA />
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import CTA from './CTA.vue';
  
  export default defineComponent({
    name: 'Header',
    components: {
       CTA
    },
  })
  </script>
  
  <style>
    .header {
        height: auto;
        padding-top: 7rem;
        overflow: hidden;
    }

    .header__container {
        text-align: center;
        height: 100%;
        position: relative;
    }
    /* CTA */
    .cta {
        margin-top: 2.5rem;
        display: flex;
        gap: 1.2rem;
        justify-content: center;
    }
  
    /* Socials */
    .socials {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.8rem;
        position: absolute;
        left: 0;
        bottom: 3rem;
    }

    .socials::after {
        content: "";
        width: 1px;
        height: 2rem;
        background: var(--color-primary);
    }
</style>