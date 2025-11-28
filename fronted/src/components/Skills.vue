<script setup>
const skills = {
  programming: [
    { name: 'Python', level: 90 },
    { name: 'Java', level: 85 },
    { name: 'C++', level: 80 },
    { name: 'JavaScript', level: 88 }
  ],
  frameworks: [
    { name: 'Vue.js', level: 85 },
    { name: 'Spring Boot', level: 82 },
    { name: 'React', level: 75 },
    { name: 'Node.js', level: 78 }
  ],
  tools: [
    { name: 'VSCode', level: 90 },
    { name: 'Git', level: 85 },
    { name: 'Docker', level: 70 },
    { name: 'Linux', level: 75 }
  ],
  soft: [
    '团队合作',
    '领导能力',
    '项目管理',
    '问题解决',
    '沟通能力'
  ]
}
</script>

<template>
  <div class="skills">
    <h2 class="section-title">个人技能</h2>
    
    <div class="skills-content">
      <div class="skills-category">
        <h3 class="category-title">编程语言</h3>
        <div class="skill-list">
          <div 
            v-for="skill in skills.programming" 
            :key="skill.name"
            class="skill-item"
          >
            <div class="skill-header">
              <span class="skill-name">{{ skill.name }}</span>
              <span class="skill-percentage">{{ skill.level }}%</span>
            </div>
            <div class="skill-bar">
              <div 
                class="skill-progress" 
                :style="{ width: skill.level + '%' }"
              ></div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="skills-category">
        <h3 class="category-title">框架与技术</h3>
        <div class="skill-list">
          <div 
            v-for="skill in skills.frameworks" 
            :key="skill.name"
            class="skill-item"
          >
            <div class="skill-header">
              <span class="skill-name">{{ skill.name }}</span>
              <span class="skill-percentage">{{ skill.level }}%</span>
            </div>
            <div class="skill-bar">
              <div 
                class="skill-progress" 
                :style="{ width: skill.level + '%' }"
              ></div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="skills-category">
        <h3 class="category-title">开发工具</h3>
        <div class="skill-list">
          <div 
            v-for="skill in skills.tools" 
            :key="skill.name"
            class="skill-item"
          >
            <div class="skill-header">
              <span class="skill-name">{{ skill.name }}</span>
              <span class="skill-percentage">{{ skill.level }}%</span>
            </div>
            <div class="skill-bar">
              <div 
                class="skill-progress" 
                :style="{ width: skill.level + '%' }"
              ></div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="skills-category">
        <h3 class="category-title">软技能</h3>
        <div class="soft-skills">
          <span 
            v-for="skill in skills.soft" 
            :key="skill"
            class="soft-skill-tag"
          >
            {{ skill }}
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.skills {
  padding: 60px 20px;
}

.section-title {
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 60px;
  color: #2c3e50;
  font-weight: 600;
  position: relative;
  padding-bottom: 20px;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 3px;
  background: #6c7a89;
}

.skills-content {
  max-width: 1000px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 40px;
}

.skills-category {
  background: rgba(255, 255, 255, 0.9);
  border-radius: 15px;
  padding: 30px;
  box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1);
}

.category-title {
  font-size: 1.4rem;
  color: #2c3e50;
  margin-bottom: 25px;
  font-weight: 600;
  padding-bottom: 15px;
  border-bottom: 2px solid #e8ecef;
}

.skill-list {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.skill-item {
  width: 100%;
}

.skill-header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 8px;
}

.skill-name {
  color: #2c3e50;
  font-weight: 500;
}

.skill-percentage {
  color: #6c7a89;
  font-size: 0.9rem;
}

.skill-bar {
  width: 100%;
  height: 8px;
  background: #e8ecef;
  border-radius: 10px;
  overflow: hidden;
}

.skill-progress {
  height: 100%;
  background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
  border-radius: 10px;
  transition: width 1s ease;
  animation: slideIn 1s ease-out;
}

@keyframes slideIn {
  from {
    width: 0;
  }
}

.soft-skills {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}

.soft-skill-tag {
  padding: 10px 20px;
  background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  color: white;
  border-radius: 25px;
  font-size: 0.9rem;
  font-weight: 500;
}

@media (max-width: 768px) {
  .skills-content {
    grid-template-columns: 1fr;
  }

  .section-title {
    font-size: 2rem;
  }
}
</style>

