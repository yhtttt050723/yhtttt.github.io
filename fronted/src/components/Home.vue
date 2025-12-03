<template>
  <div class="home">
    <div class="home-content">
      <div class="avatar-container">
        <div class="avatar">
          <img src="../../public/Main.jpg" alt="个人头像" />
        </div>
      </div>
      
      <div class="intro">
        <h1 class="name">闫鹤天</h1>
        <p class="title">前端开发工程师 | 后端开发工程师</p>
        
        <div class="bio">
          <p>
            我是一名专注于全栈开发的工程师，热爱编程和新技术探索。
            在大学期间，我积极参与各类项目和竞赛(包括CTF等安全竞赛)，积累了丰富的开发经验。
            擅长使用 Vue.js、Spring Boot 等技术栈构建现代化的 Web 应用。
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.home {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: calc(100vh - 80px);
}

.home-content {
  text-align: center;
  max-width: 800px;
  padding: 40px;
  background: rgba(255, 255, 255, 0.7);
  border-radius: 20px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(10px);
}

.avatar-container {
  margin-bottom: 30px;
}

.avatar {
  width: 200px;
  height: 200px;
  margin: 0 auto;
  border-radius: 50%;
  overflow: hidden;
  border: 5px solid rgba(255, 255, 255, 0.8);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s ease;
}

.avatar:hover {
  transform: scale(1.05);
}

.avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.intro {
  color: #2c3e50;
}

.name {
  font-size: 3rem;
  font-weight: 600;
  margin-bottom: 10px;
  color: #2c3e50;
  letter-spacing: 2px;
}

.title {
  font-size: 1.2rem;
  color: #6c7a89;
  margin-bottom: 30px;
  font-weight: 300;
}

.bio {
  text-align: left;
  line-height: 1.8;
  color: #555;
  font-size: 1.05rem;
}

.bio p {
  margin: 0;
}

@media (max-width: 768px) {
  .home-content {
    padding: 30px 20px;
  }

  .avatar {
    width: 150px;
    height: 150px;
  }

  .name {
    font-size: 2rem;
  }

  .title {
    font-size: 1rem;
  }

  .bio {
    font-size: 0.95rem;
  }
}
</style>

