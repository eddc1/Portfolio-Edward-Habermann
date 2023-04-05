<template>
    <div class="footer">
      <div class="container mx-auto">
        <a href="#home" class="footer__logo text-2xl font-medium mb-8 inline-block">
          EDWARD
        </a>
  
        <ul class="premalinks flex flex-wrap justify-center gap-8 mb-3">
          <li v-for="(link, index) in links" :key="index">
            <a :href="link.url">{{ link.text }}</a>
          </li>
        </ul>
  
        <div class="footer__socials flex justify-center gap-4 mb-16">
          <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" class="p-2 rounded-full bg-bg">
            <i class="bi bi-facebook"></i>
          </a>
          <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" class="p-2 rounded-full bg-bg">
            <i class="bi bi-instagram"></i>
          </a>
          <a href="https://twwitter.com" target="_blank" rel="noopener noreferrer" class="p-2 rounded-full bg-bg">
            <i class="bi bi-instagram"></i>
          </a>
        </div>
  
        <div class="footer__copyright">
          <small>&copy; Edward Habermann. All rights reserved.</small>
        </div>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'Footer',
    data() {
      return {
        links: [
          { text: 'Home', url: '#home' },
          { text: 'About', url: '#about' },
          { text: 'Experience', url: '#experience' },
          { text: 'Services', url: '#services' },
          { text: 'Portfolio', url: '#portfolio' },
          { text: 'Contact', url: '#contact' },
        ],
      };
    },
  });
  </script>
  
  <style scoped>

.footer {
    background: var(--color-primary);
    padding: 3rem;
    text-align: center;
    font-size: 0,9rem;
    margin-top: 7rem;
}
.footer a {
    color: var(--color-bg);
  }
  
  .footer__logo {
    margin-bottom: 2rem;
  }
  
  .premalinks {
    margin: 0 auto 3rem;
  }
  
  .footer__socials a {
    color: var(--color-white);
    border-radius: 0.7rem;
    border: 1px solid transparent;
  }
  
  .footer__socials a:hover {
    background: transparent;
    color: var(--color-bg);
    border-color: var(--color-bg);
  }
  
  @media screen and (max-width: 600px) {
    .premalinks {
      flex-direction: column;
      gap: 1.5rem;
    }
  
    .footer__socials {
      margin-bottom: 2.6rem;
    }
  }
  </style>
  