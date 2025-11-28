<script setup>
const competitions = [
  {
    name: '蓝桥杯全国软件和信息技术专业人才大赛',
    time: '2023年',
    award: '省级一等奖',
    contribution: '负责算法设计和核心功能实现，团队协作完成项目开发',
    certificate: 'https://via.placeholder.com/300x200?text=Certificate'
  },
  {
    name: 'AcWing 算法竞赛',
    time: '2023年',
    award: '全国排名前 5%',
    contribution: '独立完成多道算法题目，累计通过 500+ 道题目',
    certificate: null
  },
  {
    name: 'ACM 程序设计竞赛',
    time: '2022年',
    award: '区域赛铜奖',
    contribution: '作为核心成员参与团队训练和比赛，负责动态规划和图论算法',
    certificate: null
  }
]
</script>

<template>
  <div class="competitions">
    <h2 class="section-title">比赛经历</h2>
    
    <div class="competitions-list">
      <div 
        v-for="(competition, index) in competitions" 
        :key="index"
        class="competition-card"
      >
        <div class="competition-header">
          <h3 class="competition-name">{{ competition.name }}</h3>
          <span class="competition-time">{{ competition.time }}</span>
        </div>
        
        <div class="competition-award">
          <span class="award-badge">{{ competition.award }}</span>
        </div>
        
        <div class="competition-contribution">
          <p><strong>我的贡献：</strong>{{ competition.contribution }}</p>
        </div>
        
        <div v-if="competition.certificate" class="competition-certificate">
          <img :src="competition.certificate" alt="证书" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.competitions {
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

.competitions-list {
  max-width: 900px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.competition-card {
  background: rgba(255, 255, 255, 0.9);
  border-radius: 15px;
  padding: 30px;
  box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border-left: 4px solid #6c7a89;
}

.competition-card:hover {
  transform: translateX(10px);
  box-shadow: 0 10px 35px rgba(0, 0, 0, 0.15);
}

.competition-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 20px;
  flex-wrap: wrap;
  gap: 15px;
}

.competition-name {
  font-size: 1.4rem;
  color: #2c3e50;
  font-weight: 600;
  flex: 1;
  min-width: 200px;
}

.competition-time {
  color: #6c7a89;
  font-size: 0.95rem;
  padding: 5px 15px;
  background: #e8ecef;
  border-radius: 20px;
}

.competition-award {
  margin-bottom: 20px;
}

.award-badge {
  display: inline-block;
  padding: 8px 20px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border-radius: 25px;
  font-weight: 500;
  font-size: 0.95rem;
}

.competition-contribution {
  color: #555;
  line-height: 1.8;
  margin-bottom: 20px;
}

.competition-contribution strong {
  color: #2c3e50;
}

.competition-certificate {
  margin-top: 20px;
  border-radius: 10px;
  overflow: hidden;
  max-width: 300px;
}

.competition-certificate img {
  width: 100%;
  height: auto;
  display: block;
}

@media (max-width: 768px) {
  .competition-header {
    flex-direction: column;
  }

  .section-title {
    font-size: 2rem;
  }
}
</style>

