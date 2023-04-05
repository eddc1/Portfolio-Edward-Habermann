<template>
    <div id="about" class="py-20" style="margin-top: 8rem;">
      <div class="container mx-auto about__container">
        <div class="w-full about__me">
          <div class="about__me-image relative h-0 pb-100">
            <img
              class="absolute object-cover w-full h-full rounded-md transform hover:rotate-0 transition duration-300"
              src="../../assets/me-about.png"
              alt="About"
            />
          </div>
        </div>
        <div class="w-full about__content">
          <div class="space-y-8">
            <div class="flex items-center space-x-4">
              <i class="bi bi-award-fill about__icon"></i>
              <h3 class="text-lg font-bold">Experience</h3>
            </div>
            <p class="text-gray-600">1+ Year Working</p>
          </div>
          <div class="space-y-8">
            <div class="flex items-center space-x-4">
              <i class="bi bi-folder2-open about__icon"></i>
              <h3 class="text-lg font-bold">Projects</h3>
            </div>
            <p class="text-gray-600">4 Completed</p>
          </div>
          <div class="space-y-8">
            <div class="flex items-center space-x-4">
              <i class="bi bi-person-circle about__icon"></i>
              <h3 class="text-lg font-bold">Downloads</h3>
            </div>
            <p class="text-gray-600">1.000+ Worldwide</p>
          </div>
          <p class="text-lg mt-8">
            I'm a self-taught programmer with over a year of experience and four
            completed projects. My apps have been downloaded by over a thousand
            people worldwide. I've tried many programming languages, but I find
            frontend web development the most interesting.
          </p>
          <button
            href="#contact"
            class="btn mt-8 px-8 py-3 bg-primary text-white font-bold rounded-full transition-all hover:bg-primary-darker"
          >
            Let's Talk
          </button>
        </div>
      </div>
    </div>
  </template>
  
<script lang="ts">
import '../../style.css'
import { defineComponent } from 'vue'

export default defineComponent({
  name: "About",
  components: {
  },
})
</script>

  <style scoped>
  #about {
    margin-top: 8rem;
}

.about__container {
    display: grid;
    grid-template-columns: 35% 50%;
    gap: 15%;
}

.about__me {
    width: 100%;
    aspect-ratio: 1/1;
    border-radius: 2rem;
    background: linear-gradient(
        45deg,
        transparent,
        var(--color-primary),
        transparent
    );
    display: grid;
    place-items: center;
}

.about__me-image {
    border-radius: 2rem;
    overflow: hidden;
    transform: rotate(10deg);
    transition: var(--transition);
}

.about__me-image:hover {
    transform: rotate(0);
}

.MuiPaper {
    background-color: black;
}

.about__cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
}

.about__card {
    background: var(--color-bg-variant);
    border: 1px solid transparent;
    border-radius: 1rem;
    padding: 2rem;
    text-align: center;
    transition: var(--transistion);
}

.about__card:hover {
    background: transparent;
    border-color: var(--color-primary-variant);
    cursor: default;
}

.about__icon {
    color: var(--color-primary);
    font-size: 1.4rem;
    margin-bottom: 1rem;
}

.about__card h5 {
    font-size: 0.96rem;
}

.about__card small {
    font-size: 0.7rem;
    color: var(--color-light);
}

.about__content p {
    margin: 2rem 0 2.6rem;
    color: var(--color-light);
}

/* MEDIA QUERIES (MEDIUM DEVICES) */

@media screen and (max-width: 1024px) {
    .about__container {
        grid-template-columns: 1fr;
        gap: 0;
    }

    .about__me {
        width: 50%;
        margin: 2rem auto 4rem;
    }

    .about__content p {
        margin: 1rem 0 1.5rem;
    }
}


/* MEDIA QUERIES (SMALL DEVICES) */

@media screen and (max-width: 600px) {
    .about__me {
        width: 65%;
        margin: 0 auto 3rem;
    }

    .about__cards {
        grid-template-columns: 1fr 1fr;
        gap: 1rem;
    }

    .about__content {
        text-align: center;
    }

    .about__content p {
        margin: 1.5rem 0;
    }
}



  </style>