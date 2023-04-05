<template>
    <div>
      <nav class="nav">
        <a href="#home" @click="setActiveNav('#home')" :class="{ 'active': activeNav === '#home' }">
          <i class="bi bi-house"></i>
        </a>
        <a href="#about" @click="setActiveNav('#about')" :class="{ 'active': activeNav === '#about' }">
          <i class="bi bi-person"></i>
        </a>
        <a href="#experience" @click="setActiveNav('#experience')" :class="{ 'active': activeNav === '#experience' }">
          <i class="bi bi-book"></i>
        </a>
        <a href="#services" @click="setActiveNav('#services')" :class="{ 'active': activeNav === '#services' }">
          <i class="bi bi-tools"></i>
        </a>
        <a href="#contact" @click="setActiveNav('#contact')" :class="{ 'active': activeNav === '#contact' }">
          <i class="bi bi-chat-dots"></i>
        </a>
      </nav>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, reactive } from 'vue'
  
  export default defineComponent({
    setup() {
      const state = reactive({
        activeNav: '#'
      })
  
      const setActiveNav = (nav: string) => {
        state.activeNav = nav
      }
  
      return {
        setActiveNav,
        activeNav: state.activeNav
      }
    }
  })
  </script>
  
  <style scoped>
  .nav {
    background: rgba(0, 0, 0, 0.3);
    padding: 0.7rem 1.7rem;
    position: fixed;
    left: 50%;
    transform: translateX(-50%);
    bottom: 2rem;
    display: flex;
    gap: 0.8rem;
    border-radius: 3rem;
    backdrop-filter: blur(15px);
    z-index: 2;
  }
  
  .nav a {
    background: transparent;
    padding: 0.9rem;
    border-radius: 50%;
    display: flex;
    color: var(--color-light);
    font-size: 1.1rem;
  }
  
  .nav a:hover {
    background: rgba(128, 128, 128, 0.3);
    
  }
  
  .nav a.active {
    background: var(--color-primary);
    color: var(--color-bg);
  }
  </style>
  