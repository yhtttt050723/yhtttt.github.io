<script setup>
const socialLinks = [
  {
    name: 'GitHub',
    icon: 'github',
    url: 'https://github.com',
    color: '#24292e',
    description: '查看我的代码仓库'
  },
  {
    name: 'LinkedIn',
    icon: 'linkedin',
    url: 'https://linkedin.com',
    color: '#0077b5',
    description: '连接我的职业网络'
  },
  {
    name: 'Bilibili',
    icon: 'bilibili',
    url: 'https://bilibili.com',
    color: '#00a1d6',
    description: '观看我的视频内容'
  },
  {
    name: 'Email',
    icon: 'email',
    url: 'mailto:your.email@example.com',
    color: '#ea4335',
    description: '发送邮件联系我'
  }
]

const getIconSvg = (iconName) => {
  const icons = {
    github: `<path d="M12 2C6.477 2 2 6.477 2 12c0 4.42 2.865 8.17 6.839 9.49.5.092.682-.217.682-.482 0-.237-.008-.866-.013-1.7-2.782.603-3.369-1.34-3.369-1.34-.454-1.156-1.11-1.463-1.11-1.463-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.831.092-.646.35-1.086.636-1.336-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.029-2.683-.103-.253-.446-1.27.098-2.647 0 0 .84-.269 2.75 1.025A9.578 9.578 0 0112 6.836c.85.004 1.705.114 2.504.336 1.909-1.294 2.747-1.025 2.747-1.025.546 1.377.203 2.394.1 2.647.64.699 1.028 1.592 1.028 2.683 0 3.842-2.339 4.687-4.566 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.743 0 .267.18.578.688.48C19.138 20.167 22 16.418 22 12c0-5.523-4.477-10-10-10z"/>`,
    linkedin: `<path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>`,
    bilibili: `<path d="M17.163 4.34c1.305 0 2.366 1.061 2.366 2.367v10.585c0 1.306-1.061 2.367-2.366 2.367H6.836c-1.305 0-2.366-1.061-2.366-2.367V6.707c0-1.306 1.061-2.367 2.366-2.367h10.327zm0 1.2H6.836c-.644 0-1.166.522-1.166 1.167v10.585c0 .645.522 1.167 1.166 1.167h10.327c.644 0 1.166-.522 1.166-1.167V6.707c0-.645-.522-1.167-1.166-1.167zM8.738 8.47c.38 0 .688.308.688.688v5.686a.688.688 0 01-1.376 0V9.158c0-.38.308-.688.688-.688zm5.524 0c.38 0 .688.308.688.688v5.686a.688.688 0 01-1.376 0V9.158c0-.38.308-.688.688-.688z"/>`,
    email: `<path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>`
  }
  return icons[iconName] || ''
}
</script>

<template>
  <div class="social">
    <h2 class="section-title">个人社交</h2>
    
    <div class="social-grid">
      <a 
        v-for="(social, index) in socialLinks" 
        :key="index"
        :href="social.url"
        target="_blank"
        rel="noopener noreferrer"
        class="social-card"
        :style="{ '--card-color': social.color }"
      >
        <div class="social-icon">
          <svg viewBox="0 0 24 24" fill="currentColor" v-html="getIconSvg(social.icon)">
          </svg>
        </div>
        
        <div class="social-content">
          <h3 class="social-name">{{ social.name }}</h3>
          <p class="social-description">{{ social.description }}</p>
        </div>
        
        <div class="social-arrow">→</div>
      </a>
    </div>
  </div>
</template>

<style scoped>
.social {
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

.social-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;
}

.social-card {
  background: rgba(255, 255, 255, 0.9);
  border-radius: 15px;
  padding: 30px;
  display: flex;
  align-items: center;
  gap: 20px;
  text-decoration: none;
  color: inherit;
  box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.social-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 35px rgba(0, 0, 0, 0.15);
  border-color: var(--card-color);
}

.social-icon {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: var(--card-color);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  flex-shrink: 0;
  transition: transform 0.3s ease;
}

.social-card:hover .social-icon {
  transform: scale(1.1) rotate(5deg);
}

.social-icon svg {
  width: 30px;
  height: 30px;
}

.social-content {
  flex: 1;
}

.social-name {
  font-size: 1.3rem;
  color: #2c3e50;
  margin-bottom: 5px;
  font-weight: 600;
}

.social-description {
  color: #6c7a89;
  font-size: 0.9rem;
  margin: 0;
}

.social-arrow {
  font-size: 1.5rem;
  color: var(--card-color);
  opacity: 0;
  transition: opacity 0.3s ease, transform 0.3s ease;
  transform: translateX(-10px);
}

.social-card:hover .social-arrow {
  opacity: 1;
  transform: translateX(0);
}

@media (max-width: 768px) {
  .social-grid {
    grid-template-columns: 1fr;
  }

  .section-title {
    font-size: 2rem;
  }
}
</style>

