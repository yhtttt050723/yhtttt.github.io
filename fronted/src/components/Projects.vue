<script setup>
const projects = [
  {
    name: '项目名称 1',
    description: '这是一个项目描述，展示项目的主要功能和技术特点。',
    tech: ['Vue.js', 'Spring Boot', 'MySQL'],
    role: '前端开发、数据库设计',
    achievement: '项目成功上线，获得用户好评',
    link: 'https://github.com',
    image: 'https://via.placeholder.com/400x250?text=Project+1'
  },
  {
    name: '项目名称 2',
    description: '这是一个项目描述，展示项目的主要功能和技术特点。',
    tech: ['React', 'Node.js', 'MongoDB'],
    role: '全栈开发',
    achievement: '项目在比赛中获得一等奖',
    link: 'https://github.com',
    image: 'https://via.placeholder.com/400x250?text=Project+2'
  },
  {
    name: '项目名称 3',
    description: '这是一个项目描述，展示项目的主要功能和技术特点。',
    tech: ['Vue.js', 'Python', 'Flask'],
    role: '后端开发、API 设计',
    achievement: '优化了系统性能，响应时间提升 50%',
    link: 'https://github.com',
    image: 'https://via.placeholder.com/400x250?text=Project+3'
  }
]
</script>

<template>
  <div class="projects">
    <h2 class="section-title">项目经历</h2>
    
    <div class="projects-grid">
      <div 
        v-for="(project, index) in projects" 
        :key="index"
        class="project-card"
      >
        <div class="project-image">
          <img :src="project.image" :alt="project.name" />
        </div>
        
        <div class="project-content">
          <h3 class="project-name">{{ project.name }}</h3>
          <p class="project-description">{{ project.description }}</p>
          
          <div class="project-tech">
            <span 
              v-for="(tech, i) in project.tech" 
              :key="i"
              class="tech-tag"
            >
              {{ tech }}
            </span>
          </div>
          
          <div class="project-details">
            <p><strong>主要职责：</strong>{{ project.role }}</p>
            <p><strong>项目成果：</strong>{{ project.achievement }}</p>
          </div>
          
          <a :href="project.link" target="_blank" class="project-link">
            查看项目 →
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.projects {
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

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 40px;
  max-width: 1200px;
  margin: 0 auto;
}

.project-card {
  background: rgba(255, 255, 255, 0.9);
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
}

.project-image {
  width: 100%;
  height: 250px;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.1);
}

.project-content {
  padding: 30px;
}

.project-name {
  font-size: 1.5rem;
  color: #2c3e50;
  margin-bottom: 15px;
  font-weight: 600;
}

.project-description {
  color: #555;
  line-height: 1.6;
  margin-bottom: 20px;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-bottom: 20px;
}

.tech-tag {
  padding: 5px 15px;
  background: #e8ecef;
  border-radius: 20px;
  font-size: 0.85rem;
  color: #6c7a89;
}

.project-details {
  margin-bottom: 20px;
}

.project-details p {
  color: #555;
  margin-bottom: 8px;
  font-size: 0.95rem;
}

.project-details strong {
  color: #2c3e50;
}

.project-link {
  display: inline-block;
  color: #6c7a89;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.project-link:hover {
  color: #2c3e50;
}

@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }

  .section-title {
    font-size: 2rem;
  }
}
</style>

