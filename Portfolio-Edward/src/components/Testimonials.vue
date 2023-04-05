<template>
    <div id="testimonials" class="mt-32">
      <div class="container mx-auto px-4">
        <h5>Review from clients</h5>
        <h2>Testimonials</h2>
      </div>
      <div class="container mx-auto px-4">
        <swiper
            class="testimonials__container"
            :spaceBetween="30"
            :centeredSlides="true"
            :pagination="{
                clickable: true,
            }"
            :navigation="true"
            :modules="modules"
            :effect="'cube'"
            :grabCursor="true"
            :cubeEffect="{
            shadow: true,
            slideShadows: true,
            shadowOffset: 20,
            shadowScale: 0.94,
        }"
        >
          <swiper-slide v-for="(testimonial, index) in testimonials" :key="index" class="testimonial">
            <div class="client__avatar rounded-full overflow-hidden border-primary-variant border-8 mx-auto">
              <img :src="testimonial.avatar" :alt="testimonial.name" width="50" height="50"/>
            </div>
            <h5 class="client__name">{{ testimonial.name }}</h5>
            <small class="client__review">{{ testimonial.review }}</small>
          </swiper-slide>
        </swiper>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import {Autoplay, Pagination, Navigation, EffectCube} from 'swiper';
  import { Swiper, SwiperSlide } from 'swiper/vue';
  import 'swiper/swiper-bundle.min.css';
  import Avt1 from '../assets/avatar1.jpg';
  import Avt2 from '../assets/avatar2.jpg';
  import Avt3 from '../assets/avatar3.jpg';
  import Avt4 from '../assets/avatar4.jpg';
  
  interface Testimonial {
    avatar: string;
    name: string;
    review: string;
  }
  
  export default defineComponent({
    components: {
      Swiper,
      SwiperSlide,
    },
    data() {
      const testimonials: Testimonial[] = [
        {
          avatar: Avt1,
          name: 'Sarah Smith',
          review:
            "Edward's web development expertise was evident from the start. He was responsive, attentive to detail, and met all deadlines. Our website looks better than ever, and we highly recommend him for any web development needs.",
        },
        {
          avatar: Avt2,
          name: 'Jack Brown',
          review:
            "Edward's web development skills are top-notch. He's reliable, responsive, and always delivers high-quality work. I would definitely recommend him to anyone looking for a talented developer.",
        },
        {
          avatar: Avt3,
          name: 'Michael Lee',
          review:
            "I had the pleasure of working with Edward on a web development project, and I couldn't be happier with the results. He's a true professional, and his expertise in the field is exceptional. I would definitely work with Edward again in the future",
        },
        {
          avatar: Avt4,
          name: 'Tina Snow',
          review:
            "Edward is an outstanding programmer who goes above and beyond to ensure the success of his projects. He's easy to work with and always delivers on time. I would highly recommend Edward to anyone looking for a skilled web developer.",
        },
      ];
      return {
        testimonials,
      };
    },
    setup() {
      return {
        modules: [Autoplay, Pagination, Navigation, EffectCube],
      };
    },
  });
  </script>
  
<style>
#testimonials {
    margin-top: 8rem;
}

.container.testimonials__container {
    width: 40%;
    padding-bottom: 4rem;
}

.client__avatar {
    width: 4rem;
    aspect-ratio: 1/1;
    overflow: hidden;
    border-radius: 50%;
    margin: 0 auto 1rem;
    border: 0.4rem solid var(--color-primary-variant);
}

.testimonial {
    background: var(--color-bg-variant);
    text-align: center;
    padding: 2rem;
    border-radius: 2rem;
    user-select: none;
}

.client__review {
    color: var(--color-light);
    font-weight: 300;
    display: block;
    width: 80%;
    margin: 0.8rem auto 0;
}

.swiper-pagination-clickable
.swiper-pagination-bullet {
    background: var(--color-primary);
}

/* MEDIA QUERIES (MEDIUM DEVICES) */

@media screen and (max-width: 1024px) {
    .container.testimonials__container {
        width: 70%;
    }
}


/* MEDIA QUERIES (SMALL DEVICES) */

@media screen and (max-width: 600px) {
    .container.testimonials__container {
        width: var(--container-width-sm);
    }

    .client__review {
        width: var(--container-width-sm);
    }
}

.swiper-button-prev,
.swiper-button-next {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 30px;
  height: 30px;
  border-radius: 50%;
  cursor: pointer;
  z-index: 10;
}

.swiper-button-prev {
  left: 20px;
}

.swiper-button-next {
  right: 20px;
}

.swiper-button-prev::before,
.swiper-button-next::before {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 10px;
  height: 10px;
  border-top: 2px solid black;
  border-right: 2px solid black;
}

.swiper-button-prev::before {
  transform: translate(-50%, -50%) rotate(-45deg);
}

.swiper-button-next::before {
  transform: translate(-50%, -50%) rotate(135deg);
}

</style>