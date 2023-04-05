<template>
    <div id="portfolio">
      <div class="container mx-auto">
        <h5>My Recent Work</h5>
        <h2>
          Portfolio
        </h2>
      </div>
  
      <div class="container portfolio__container">
        <article v-for="item in data" :key="item.id" class="portfolio__item">
          <div class="portfolio__item-image">
            <img
              :src="item.image"
              alt="Portfolio Image"
              layout="fill"
              object-fit="cover"
              class="rounded-t-lg"
            />
          </div>
          <div class="p-6">
            <h3>{{ item.title }}</h3>
            <div class="portfolio__item-cta">
                <a :href="item.github" target="_blank" rel="noopener noreferrer">
                <button class="btn">
                  Github
                </button>
              </a>
              <a :href="item.demo" target="_blank" rel="noopener noreferrer">
                <button class="btn">
                  Live Demo
                </button>
              </a>
            </div>
          </div>
        </article>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import IMG1 from '../assets/portfolio1.jpg';
  import IMG2 from '../assets/portfolio2.jpg';
  import IMG3 from '../assets/portfolio3.jpg';
  
  const data = [
    {
      id: 1,
      image: IMG1,
      title: "Portfolio",
      github: 'https://github.com/eddc1/Portfolio',
      demo: 'https://dribbble.com/shots/',
    },
    {
      id: 2,
      image: IMG2,
      title: 'Blog Potwarmer',
      github: 'https://github.com/eddc1/Potwarmer',
      demo: 'https://dribbble.com/shots/',
    },
    {
      id: 3,
      image: IMG3,
      title: 'News Ticker',
      github: 'https://github.com/eddc1/NewsTicker',
      demo: 'https://dribbble.com/shots/',
    },
  ];
  
  export default defineComponent({
    name: 'Portfolio',
    data() {
      return {
        data,
      };
    },
  });
  </script>

<style>
    #portfolio {
        margin-top: 8rem;
    }

    .portfolio__container {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 2.5rem;
    }

    .portfolio__item {
        background: var(--color-bg-variant);
        padding: 1.2rem;
        border-radius: 2rem;
        border: 1px solid transparent;
        transition: var(--transition);
    }

    .portfolio__item:hover {
        border-color: var(--color-primary-variant);
        background: transparent;
    }

    .portfolio__item-image {
        border-radius: 1.5rem;
        overflow: hidden;
    }

    .portfolio__item h3 {
        margin: 1.2rem 0 2rem;
    }

    .portfolio__item-cta {
        display: flex;
        gap: 1rem;
        margin-bottom: 1rem;
    }

    /* MEDIA QUERIES (MEDIUM DEVICES) */

    @media screen and (max-width: 1024px) {
        .portfolio__container {
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }
    }


    /* MEDIA QUERIES (SMALL DEVICES) */

    @media screen and (max-width: 600px) {
        .portfolio__container {
            grid-template-columns: 1fr;
            gap: 1rem;
        }
    }
</style>
  