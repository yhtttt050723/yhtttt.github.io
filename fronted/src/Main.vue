<script setup>
import { ref } from 'vue'
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import Projects from './components/Projects.vue'
import Competitions from './components/Competitions.vue'
import Education from './components/Education.vue'
import Skills from './components/Skills.vue'
import Social from './components/Social.vue'
import Contact from './components/Contact.vue'

const currentSection = ref('home')

const scrollToSection = (section) => {
  currentSection.value = section
  setTimeout(() => {
    const element = document.getElementById(section)
    if (element) {
      const offset = 80
      const elementPosition = element.getBoundingClientRect().top
      const offsetPosition = elementPosition + window.pageYOffset - offset
      
      window.scrollTo({
        top: offsetPosition,
        behavior: 'smooth'
      })
    }
  }, 100)
}
</script>

<template>
  <div class="app">
    <Navbar @navigate="scrollToSection" :current-section="currentSection" />
    
    <main>
      <section id="home">
        <Home />
      </section>
      
      <section id="projects">
        <Projects />
      </section>
      
      <section id="competitions">
        <Competitions />
      </section>
      
      <section id="education">
        <Education />
      </section>
      
      <section id="skills">
        <Skills />
      </section>
      
      <section id="social">
        <Social />
      </section>
      
      <section id="contact">
        <Contact />
      </section>
    </main>
  </div>
</template>

<style scoped>
.app {
  min-height: 100vh;
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
}

main {
  padding-top: 80px;
}

section {
  min-height: 100vh;
  padding: 80px 20px;
  max-width: 1200px;
  margin: 0 auto;
}

@media (max-width: 768px) {
  section {
    padding: 60px 15px;
  }
}
</style>
