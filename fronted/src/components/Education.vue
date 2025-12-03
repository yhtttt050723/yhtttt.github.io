<template>
  <div class="education">
    <h2 class="section-title">教育背景</h2>
    
    <div class="education-content">
      <div class="education-card">
        <div class="education-icon">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M22 10v6M2 10l10-5 10 5-10 5z" />
            <path d="M6 12v5c0 1.1.9 2 2 2h8c1.1 0 2-.9 2-2v-5" />
          </svg>
        </div>
        
        <div class="education-details">
          <h3 class="school-name">上海理工大学</h3>
          <p class="degree">本科 | 计算机科学与技术</p>
          <p class="period">2023年 - 2027年</p>
          
          <div class="academic-performance">
            <div class="gpa">
              <span class="label">GPA：</span>
              <span class="value">3.6/ 4.5</span>
            </div>

          </div>
          
          <div class="achievements">
            <h4>学术成就：</h4>
            <ul>
              <li>多次获得校级奖学金</li>
              <li>参与科研项目 2 项</li>
            </ul>
          </div>
          
          <div class="courses">
            <h4>核心课程：</h4>
            <div class="course-tags">
              <span>数据结构</span>
              <span>计算机网络</span>
              <span>数据库系统(双语)</span>
              <span>操作系统</span>
              <span>人工智能</span>
              <span>项目管理与过程改进</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.education {
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

.education-content {
  max-width: 900px;
  margin: 0 auto;
}

.education-card {
  background: rgba(255, 255, 255, 0.9);
  border-radius: 20px;
  padding: 50px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
  display: flex;
  gap: 40px;
  align-items: flex-start;
}

.education-icon {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  flex-shrink: 0;
}

.education-icon svg {
  width: 40px;
  height: 40px;
}

.education-details {
  flex: 1;
}

.school-name {
  font-size: 2rem;
  color: #2c3e50;
  margin-bottom: 10px;
  font-weight: 600;
}

.degree {
  font-size: 1.2rem;
  color: #6c7a89;
  margin-bottom: 5px;
}

.period {
  color: #999;
  margin-bottom: 30px;
}

.academic-performance {
  display: flex;
  gap: 40px;
  margin-bottom: 30px;
  padding: 20px;
  background: #f8f9fa;
  border-radius: 10px;
}

.gpa, .ranking {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.label {
  color: #6c7a89;
  font-size: 0.9rem;
}

.value {
  color: #2c3e50;
  font-size: 1.5rem;
  font-weight: 600;
}

.achievements, .courses {
  margin-bottom: 30px;
}

.achievements h4, .courses h4 {
  color: #2c3e50;
  margin-bottom: 15px;
  font-size: 1.1rem;
}

.achievements ul {
  list-style: none;
  padding: 0;
}

.achievements li {
  color: #555;
  margin-bottom: 10px;
  padding-left: 25px;
  position: relative;
}

.achievements li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #667eea;
  font-weight: bold;
}

.course-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.course-tags span {
  padding: 8px 20px;
  background: #e8ecef;
  border-radius: 20px;
  color: #6c7a89;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .education-card {
    flex-direction: column;
    padding: 30px 20px;
  }

  .academic-performance {
    flex-direction: column;
    gap: 20px;
  }

  .section-title {
    font-size: 2rem;
  }
}
</style>

