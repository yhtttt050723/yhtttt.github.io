<script setup>
import { ref } from 'vue'

const formData = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const isSubmitting = ref(false)
const submitStatus = ref(null)

const handleSubmit = async (e) => {
  e.preventDefault()
  isSubmitting.value = true
  submitStatus.value = null

  // 这里可以连接到后端 API
  // 暂时模拟提交
  setTimeout(() => {
    isSubmitting.value = false
    submitStatus.value = 'success'
    formData.value = { name: '', email: '', subject: '', message: '' }
    
    setTimeout(() => {
      submitStatus.value = null
    }, 3000)
  }, 1000)
}
</script>

<template>
  <div class="contact">
    <h2 class="section-title">联系我</h2>
    
    <div class="contact-content">
      <div class="contact-info">
        <h3>让我们开始对话</h3>
        <p>如果您对我的项目或经历感兴趣，或者有任何问题，欢迎通过以下方式联系我。</p>
        
        <div class="contact-methods">
          <div class="contact-method">
            <div class="method-icon">📧</div>
            <div>
              <strong>邮箱</strong>
              <p>your.email@example.com</p>
            </div>
          </div>
          
          <div class="contact-method">
            <div class="method-icon">📱</div>
            <div>
              <strong>电话</strong>
              <p>+86 138-0000-0000</p>
            </div>
          </div>
          
          <div class="contact-method">
            <div class="method-icon">📍</div>
            <div>
              <strong>地址</strong>
              <p>上海市杨浦区</p>
            </div>
          </div>
        </div>
      </div>
      
      <form class="contact-form" @submit="handleSubmit">
        <div class="form-group">
          <label for="name">姓名</label>
          <input 
            type="text" 
            id="name" 
            v-model="formData.name" 
            required
            placeholder="请输入您的姓名"
          />
        </div>
        
        <div class="form-group">
          <label for="email">邮箱</label>
          <input 
            type="email" 
            id="email" 
            v-model="formData.email" 
            required
            placeholder="请输入您的邮箱"
          />
        </div>
        
        <div class="form-group">
          <label for="subject">主题</label>
          <input 
            type="text" 
            id="subject" 
            v-model="formData.subject" 
            required
            placeholder="请输入邮件主题"
          />
        </div>
        
        <div class="form-group">
          <label for="message">消息</label>
          <textarea 
            id="message" 
            v-model="formData.message" 
            required
            rows="6"
            placeholder="请输入您的消息..."
          ></textarea>
        </div>
        
        <button 
          type="submit" 
          class="submit-btn"
          :disabled="isSubmitting"
        >
          {{ isSubmitting ? '发送中...' : '发送消息' }}
        </button>
        
        <div v-if="submitStatus === 'success'" class="submit-success">
          消息已成功发送！
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
.contact {
  padding: 60px 20px;
  background: rgba(255, 255, 255, 0.5);
  border-radius: 20px;
  margin: 20px;
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

.contact-content {
  max-width: 1000px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  gap: 60px;
}

.contact-info h3 {
  font-size: 1.8rem;
  color: #2c3e50;
  margin-bottom: 15px;
  font-weight: 600;
}

.contact-info > p {
  color: #555;
  line-height: 1.8;
  margin-bottom: 40px;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.contact-method {
  display: flex;
  align-items: flex-start;
  gap: 15px;
}

.method-icon {
  font-size: 1.5rem;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #f8f9fa;
  border-radius: 50%;
  flex-shrink: 0;
}

.contact-method strong {
  display: block;
  color: #2c3e50;
  margin-bottom: 5px;
}

.contact-method p {
  color: #6c7a89;
  margin: 0;
  font-size: 0.95rem;
}

.contact-form {
  background: rgba(255, 255, 255, 0.9);
  padding: 40px;
  border-radius: 15px;
  box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 25px;
}

.form-group label {
  display: block;
  color: #2c3e50;
  margin-bottom: 8px;
  font-weight: 500;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 12px 15px;
  border: 2px solid #e8ecef;
  border-radius: 8px;
  font-size: 1rem;
  font-family: inherit;
  transition: border-color 0.3s ease;
  background: white;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #667eea;
}

.form-group textarea {
  resize: vertical;
}

.submit-btn {
  width: 100%;
  padding: 15px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 5px 20px rgba(102, 126, 234, 0.4);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.submit-success {
  margin-top: 15px;
  padding: 12px;
  background: #d4edda;
  color: #155724;
  border-radius: 8px;
  text-align: center;
  font-weight: 500;
}

@media (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .contact-form {
    padding: 30px 20px;
  }

  .section-title {
    font-size: 2rem;
  }
}
</style>

