<template>

  <div>
    <Header />
    <Nav />
    <About />
    <Experience />
    <Services />
    <Portfolio />
    <Testimonials />
    <Contact />
    <Footer />   
  </div>

</template>


<script lang="ts">

import { defineComponent } from 'vue'
import Header from './components/Header.vue';
import Nav from './components/Nav.vue';
import About from './components/About.vue'
import Experience from './components/Experience.vue';
import Services from './components/Services.vue';
import Portfolio from './components/Portfolio.vue';
import Testimonials from './components/Testimonials.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';


export default defineComponent({
  name: 'App',
  components: {
    Nav,
    Header,
    About,
    Experience,
    Services,
    Portfolio,
    Testimonials,
    Contact,
    Footer,
  },
});
</script>

