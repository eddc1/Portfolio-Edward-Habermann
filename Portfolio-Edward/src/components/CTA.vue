<template>
    <div class="cta">
      <button
        class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
        @click="downloadCV"
      >
        Download CV
      </button>
      <button class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Let's Talk
      </button>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import CV from '../assets/Edward_Habermann_Lebenslauf.png';
  
  export default defineComponent({
    name: 'CTA',
    methods: {
      downloadCV() {
        const link = document.createElement('a');
        link.href = CV;
        link.download = 'Edward_Habermann_Lebenslauf.png';
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
      }
    }
  });
  </script>
  
  <style scoped>

.btn {
    background-color: #4f46e5;
    color: #fff;
    padding: 10px 20px;
    font-size: 16px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    margin-right: 10px;
  }
  
  .btn:hover {
    background-color: #332db5;
  }

  </style>
  