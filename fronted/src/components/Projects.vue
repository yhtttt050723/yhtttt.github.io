<script setup>
const projects = [
  {
    name: '安全网站分析系统',
    description: '随着网络安全威胁的不断升级，传统的基于规则的安全分析工具已难以满足需求。本项目开发了一款基于AI的网站安全分析系统，专注于提升检测效率和准确性。该系统利用机器学习算法自动识别网站中的安全漏洞、恶意代码及钓鱼攻击，并实时监控网站安全状态，及时预警潜在风险。\n' +
        '本项目的亮点在于其强大的互动性和智能化水平。通过分布式爬虫技术，系统能够实时搜集最新数据，并使用先进的AI模型（如ResNet18和Transformer）对网页图像和文本进行深度分析，精准判断网站是否存在黄色、赌博或诈骗等风险。此外，前端采用Vue框架实现直观的数据可视化展示，后端则使用FastApi确保系统的高效响应。\n' +
        '与传统工具相比，此方案不仅增强了安全检测的准确性和效率，还提供了详细的多维度安全报告，帮助用户更好地理解并管理网站安全性。因此，本系统在提高互联网环境的安全性方面展现了巨大的潜力和价值。',
    tech: ['Vue.js', 'Spring Boot', 'Python'],
    role: '前端开发',
    achievement: '市级大创项目,上海市计算机应用能力大赛国家级二等奖',
    link: 'https://github.com/caodong0225/frontend#',
    image: '../../public/WebSafe.png'
  },
  {
    name: '项目管理与过程改进学习网站',
    description: '这是一个项目描述，展示项目的主要功能和技术特点。',
    tech: ['Vue3','SpringBoot'],
    role: '项目经理 全栈开发',
    achievement: '项目在比赛中获得一等奖',
    link: 'https://github.com/yhtttt050723/USST_SPM_COURSE',
    image: 'https://via.placeholder.com/400x250?text=Project+2'
  },
  {
    name: '大学生信息资源分享平台',
    description: '这是一个项目描述，展示项目的主要功能和技术特点。',
    tech: ['Vue.js','SpringBoot'],
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

