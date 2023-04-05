<template>
    <div class="experience" id="experience">

        <div class="container">
        <!-- Hier kommt der Inhalt der Seite -->
            <h5>What Skills I Have</h5>
            <h2>My Experience</h2>
        </div>
  
      <div class="container experience__container">
        <div class="experience__frontend">
          <h3>
            Frontend Development
          </h3>
          <div class="experience__content px-6 py-4">
            <div
              v-for="(skill, index) in frontendSkills"
              :key="index"
              class="experience__details"
            >
            <i class="bi bi-check-circle"></i>
              <div>
                <h4 class="text-lg font-bold ">{{ skill.name }}</h4>
                <small class="text-gray-600">{{ skill.level }}</small>
              </div>
            </div>
          </div>
        </div>
  
        <div class="experience__backend">
          <h3>
            Backend Development
          </h3>
          <div class="experience__content">
            <div
              v-for="(skill, index) in backendSkills"
              :key="index"
              class="experience__details items-center py-2"
            >
            <i class="bi bi-check-circle"></i>
              <div>
                <h4 class="text-lg font-bold text-gray-600">{{ skill.name }}</h4>
                <small class="text-gray-600">{{ skill.level }}</small>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from "vue";
//   import CheckCircleIcon from "@mui/icons-material/CheckCircle";
  
  export default defineComponent({
    name: "Experience",
    components: {
    //   Container,
    //   CheckCircleIcon,
    },
    data() {
      return {
        frontendSkills: [
          { name: "HTML", level: "Experienced" },
          { name: "JavaScript", level: "Experienced" },
          { name: "Bootstrap", level: "Experienced" },
          { name: "Material UI", level: "Experienced" },
          { name: "React JS", level: "Experienced" },
          { name: "Vue JS", level: "Experienced" },
          { name: "Tailwind CSS", level: "Experienced" },
        ],
        backendSkills: [
          { name: "Node Js", level: "Experienced" },
          { name: "MongoDB", level: "Basic" },
          { name: "PHP", level: "Basic" },
          { name: "Python", level: "Experienced" },
          { name: "C++", level: "Experienced" },
          { name: "Java", level: "Experienced" },
        ],
      };
    },
  });
  </script>
  
  <style scoped>
  #experience {
    margin-top: 8rem;
}

.experience__container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
}

.experience__container > div {
    background: var(--color-bg-variant);
    padding: 2.4rem 5rem;
    border-radius: 2rem;
    border: 1px solid transparent;
    transition: var(--transition);
}

.experience__container > div:hover {
    background: transparent;
    border-color: var(--color-primary-variant);
    cursor: default;
}

.experience__container > div h3 {
    text-align: center;
    margin-bottom: 2rem;
    color: var(--color-primary);
}

.experience__content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    row-gap: 2rem;
}

.experience__details {
    display: flex;
    gap: 1rem;
}

.experience__details-icon {
    margin-top: 6px;
    color: var(--color-primary);
}


/* MEDIA QUERIES (HIGH DEVICES) */

@media screen and (max-width: 1024px) {
    .experience__container {
        grid-template-columns: 1fr;
    }

    .experience__container > div {
        width: 80%;
        padding: 2rem;
        margin: 0 auto;
    }

    .experience__content {
        padding: 1rem;
    }
}


/* MEDIA QUERIES (SMALL DEVICES) */

@media screen and (max-width: 600px) {
    .experience__container {
        gap: 1rem;
    }

    .experience__container > div {
        width: 100%;
        padding: 2rem 1rem;
    }
}
  </style>

  