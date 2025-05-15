<script setup>
const stats = [
  { number: '15+', text: 'Years of Experience' },
  { number: '500+', text: 'Projects Completed' },
  { number: '99.9%', text: 'Network Uptime' },
  { number: '24/7', text: 'Support Available' }
];
</script>

<template>
  <section id="about" class="about">
    <div class="container">
      <div class="about-wrapper">
        <div class="about-content">
          <h2>About WorkNet</h2>
          <p class="lead">We're a team of network specialists dedicated to delivering innovative IT solutions since 2010.</p>
          <p>At WorkNet, we understand that reliable network infrastructure is the backbone of modern business operations. Our expert team designs, implements, and maintains custom network solutions that scale with your business needs.</p>
          <p>With a client-focused approach and commitment to excellence, we provide responsive support and forward-thinking strategies to keep your technology aligned with your business goals.</p>
          <ul class="about-features">
            <li>
              <span class="checkmark">✓</span>
              Enterprise-grade infrastructure
            </li>
            <li>
              <span class="checkmark">✓</span>
              Certified network professionals
            </li>
            <li>
              <span class="checkmark">✓</span>
              Proactive monitoring
            </li>
            <li>
              <span class="checkmark">✓</span>
              Scalable solutions
            </li>
          </ul>
        </div>
        <div class="about-stats">
          <div v-for="(stat, index) in stats" :key="index" class="stat-card">
            <h3>{{ stat.number }}</h3>
            <p>{{ stat.text }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 6rem 0;
  background-color: #2c2c2e;
  position: relative;
  overflow: hidden;
}

.about::before {
  content: '';
  position: absolute;
  top: -150px;
  right: -150px;
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(66, 190, 114, 0.1) 0%, rgba(66, 190, 114, 0) 70%);
  z-index: 1;
}

.about::after {
  content: '';
  position: absolute;
  bottom: -200px;
  left: -200px;
  width: 400px;
  height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(138, 43, 226, 0.08) 0%, rgba(138, 43, 226, 0) 70%);
  z-index: 1;
}

.about-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  position: relative;
  z-index: 2;
}

.about-content h2 {
  font-size: 2.5rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 1.5rem;
  position: relative;
}

.about-content h2::after {
  content: '';
  position: absolute;
  width: 60px;
  height: 3px;
  background-color: #8a2be2;
  bottom: -15px;
  left: 0;
}

.about-content .lead {
  font-size: 1.3rem;
  line-height: 1.5;
  color: #e0e0e0;
  margin-bottom: 1.5rem;
  font-weight: 500;
}

.about-content p {
  font-size: 1rem;
  line-height: 1.8;
  color: #c0c0c0;
  margin-bottom: 1rem;
}

.about-features {
  list-style: none;
  padding: 0;
  margin: 2rem 0 0;
}

.about-features li {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
  font-size: 1.05rem;
  color: #e0e0e0;
}

.checkmark {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  width: 24px;
  height: 24px;
  background: linear-gradient(135deg, #8a2be2 0%, #42be72 100%);
  border-radius: 50%;
  margin-right: 1rem;
  font-size: 0.8rem;
  color: #ffffff;
}

.about-stats {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
  align-content: center;
}

.stat-card {
  background: rgba(28, 28, 30, 0.5);
  border-radius: 12px;
  padding: 2rem;
  text-align: center;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.stat-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.stat-card h3 {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  background: linear-gradient(90deg, #8a2be2, #42be72);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.stat-card p {
  font-size: 1rem;
  color: #e0e0e0;
}

@media screen and (max-width: 1024px) {
  .about-wrapper {
    gap: 2rem;
  }
}

@media screen and (max-width: 768px) {
  .about {
    padding: 4rem 0;
  }
  
  .about-wrapper {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  
  .about-content h2 {
    font-size: 2rem;
  }
  
  .about-content .lead {
    font-size: 1.2rem;
  }
}

@media screen and (max-width: 480px) {
  .about-stats {
    grid-template-columns: 1fr;
  }
  
  .stat-card {
    padding: 1.5rem;
  }
  
  .stat-card h3 {
    font-size: 2rem;
  }
}
</style>