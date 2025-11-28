<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const props = defineProps({
  currentSection: String
})

const emit = defineEmits(['navigate'])
const isScrolled = ref(false)
const activeSection = ref('home')

const sections = [
  { id: 'home', label: '首页' },
  { id: 'projects', label: '项目经历' },
  { id: 'competitions', label: '比赛经历' },
  { id: 'education', label: '教育背景' },
  { id: 'skills', label: '个人技能' },
  { id: 'social', label: '社交' },
  { id: 'contact', label: '联系' }
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
  
  // 更新当前激活的section
  const scrollPosition = window.scrollY + 100
  for (let i = sections.length - 1; i >= 0; i--) {
    const section = document.getElementById(sections[i].id)
    if (section && section.offsetTop <= scrollPosition) {
      activeSection.value = sections[i].id
      break
    }
  }
}

const navigate = (section) => {
  emit('navigate', section)
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <nav class="navbar" :class="{ scrolled: isScrolled }">
    <div class="navbar-container">
      <div class="logo">个人简历</div>
      <ul class="nav-menu">
        <li 
          v-for="item in sections" 
          :key="item.id"
          :class="{ active: activeSection === item.id || currentSection === item.id }"
          @click="navigate(item.id)"
        >
          {{ item.label }}
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  z-index: 1000;
  transition: all 0.3s ease;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
}

.navbar.scrolled {
  background: rgba(255, 255, 255, 0.95);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 70px;
}

.logo {
  font-size: 1.5rem;
  font-weight: 600;
  color: #2c3e50;
  letter-spacing: 1px;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 30px;
  margin: 0;
  padding: 0;
}

.nav-menu li {
  cursor: pointer;
  color: #555;
  font-size: 0.95rem;
  transition: color 0.3s ease;
  position: relative;
  padding: 5px 0;
}

.nav-menu li::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: #6c7a89;
  transition: width 0.3s ease;
}

.nav-menu li:hover,
.nav-menu li.active {
  color: #2c3e50;
}

.nav-menu li:hover::after,
.nav-menu li.active::after {
  width: 100%;
}

@media (max-width: 768px) {
  .navbar-container {
    flex-direction: column;
    height: auto;
    padding: 15px 20px;
  }

  .nav-menu {
    flex-wrap: wrap;
    gap: 15px;
    justify-content: center;
    margin-top: 10px;
  }

  .nav-menu li {
    font-size: 0.85rem;
  }
}
</style>

