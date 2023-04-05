<template>
    <div id="services">
        <div class="container">
            <h5>What I Offer</h5>
            <h2>Services</h2>
        </div>
      <div class="container services__container">
          <div v-for="(service, index) in services" :key="index" className="service">
              <div class="service__head">
                <h3>{{ service.title }}</h3>
              </div>
              <ul class="service__list">
                <li v-for="(item, index) in service.items" :key="index">
                    <i class="bi bi-check-circle service__list-icon"></i>
                    <p>{{ item }}</p>
                </li>
              </ul>
          </div>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'Services',

    data() {
      return {
        services: [
          {
            title: 'Ui/Ux Design',
            items: [
              'Creating user-friendly designs that take into account the needs of the users.',
              'Developing wireframes and prototypes to visualize the design concept.',
              'Using modern design tools and technologies to create visually appealing interfaces.',
              'Considering color schemes, typography, and visual hierarchy to ensure a consistent and user-friendly experience.',
              'Adhering to industry standards and best practices to ensure optimal user experience.',
              'Working closely with clients to understand their requirements and needs and integrate them into the design concept.'
            ]
          },
          {
            title: 'Web Development',
            items: [
              'Developing responsive and scalable websites using the latest web technologies and frameworks.',
              'Writing clean, efficient, and maintainable code that follows industry standards and best practices.',
              'Optimizing website performance and loading times for a seamless user experience.',
              'Incorporating SEO best practices to improve website visibility and ranking on search engines.',
              'Integrating third-party APIs and services to add additional functionality and enhance user experience.',
              'Providing ongoing website maintenance and support to ensure website functionality and security.'
            ]
          },
          {
            title: 'Content Creation',
            items: [
              'Developing high-quality and engaging content that resonates with the target audience and aligns with the brand\'s tone and voice.',
              'Conducting thorough research to ensure accuracy and relevance of the content.',
              'Incorporating search engine optimization (SEO) best practices to improve content visibility and ranking on search engines.',
              'Creating content that is shareable on social media platforms and other relevant channels.',
              'Providing content strategy development to help brands align their content efforts with their business goals.'
            ]
          }
        ]
      }
    }
  })
  </script>
  

<style>

#services {
    margin-top: 8rem;
}

.services__container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 3rem;
}

.service {
    background: var(--color-bg-variant);
    border-radius: 0 0 2rem 2rem;
    border: 1px solid var(--color-primary);
    transition: var(--transition);
    display: flex;
    flex-direction: column;
}

.service:hover {
    background: transparent;
    border-color: var(--color-primary-variant);
    cursor: default;
}

.service__head {
    background: var(--color-primary);
    padding: 2rem;
    border-radius:0 0 2rem 2rem;
    box-shadow: 0 2rem 1rem rgba(0, 0, 0, 0.1);
    flex: 0 0 auto;
}

.service__head h3 {
    color: var(--color-bg);
    font-size: 1rem;
    text-align: center;
}

.service__list {
    padding: 2rem;
    flex: 1 1 auto;
}

.service__list li {
    display: flex;
    gap: 1rem;
    margin-bottom: 0.8rem;
}

.service__list-icon {
    color: var(--color-primary);
    margin-top: 2px;
}

.service__list p {
    font-size: 0.9rem;
}


/* MEDIA QUERIES (MEDIUM DEVICES) */

@media screen and (max-width: 1024px) {
    .services__container {
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 2rem;
    }
}


/* MEDIA QUERIES (SMALL DEVICES) */

@media screen and (max-width: 600px) {
    .services__container {
        grid-template-columns: 1fr;
        gap: 1.5rem;
    }
}



</style>