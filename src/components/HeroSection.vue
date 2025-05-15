<script setup>
</script>

<template>
  <section id="home" class="hero">
    <div class="container">
      <div class="hero-content">
        <h1 class="fade-in">Network Solutions for the Modern Enterprise</h1>
        <p class="fade-in-delay">Secure, reliable, and scalable network infrastructure designed for your business needs</p>
        <div class="hero-buttons fade-in-delay-2">
          <a href="#contact" class="btn btn-primary">Get Started</a>
          <a href="#services" class="btn btn-secondary">Explore Services</a>
        </div>
      </div>
      <div class="hero-shape">
        <div class="gradient-circle"></div>
        <div class="gradient-circle small"></div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, #1c1c1e 0%, #2c2c2e 100%);
  padding-top: 80px;
}

.hero-content {
  max-width: 720px;
  position: relative;
  z-index: 2;
  padding: 2rem 0;
}

.hero h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  line-height: 1.2;
  background: linear-gradient(90deg, #ffffff 0%, #e0e0e0 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-fill-color: transparent;
}

.hero p {
  font-size: 1.25rem;
  line-height: 1.6;
  margin-bottom: 2.5rem;
  color: #d0d0d0;
  max-width: 600px;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.hero-shape {
  position: absolute;
  top: 50%;
  right: 5%;
  transform: translateY(-50%);
  z-index: 1;
}

.gradient-circle {
  width: 450px;
  height: 450px;
  background: radial-gradient(circle, rgba(138, 43, 226, 0.2) 0%, rgba(138, 43, 226, 0) 70%);
  border-radius: 50%;
  animation: pulse 8s infinite alternate;
}

.gradient-circle.small {
  width: 250px;
  height: 250px;
  position: absolute;
  top: -100px;
  right: -100px;
  background: radial-gradient(circle, rgba(66, 190, 114, 0.15) 0%, rgba(66, 190, 114, 0) 70%);
  animation: pulse 6s infinite alternate-reverse;
}

@keyframes pulse {
  0% {
    transform: scale(1);
    opacity: 0.5;
  }
  100% {
    transform: scale(1.2);
    opacity: 0.8;
  }
}

.fade-in {
  animation: fadeIn 1s ease-out;
}

.fade-in-delay {
  animation: fadeIn 1s ease-out 0.3s forwards;
  opacity: 0;
}

.fade-in-delay-2 {
  animation: fadeIn 1s ease-out 0.6s forwards;
  opacity: 0;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media screen and (max-width: 1024px) {
  .hero h1 {
    font-size: 3rem;
  }
  
  .hero-shape {
    right: -15%;
  }
}

@media screen and (max-width: 768px) {
  .hero h1 {
    font-size: 2.5rem;
  }
  
  .hero p {
    font-size: 1.1rem;
  }
  
  .hero-shape {
    opacity: 0.4;
  }
}

@media screen and (max-width: 480px) {
  .hero h1 {
    font-size: 2rem;
  }
  
  .hero p {
    font-size: 1rem;
  }
  
  .hero-buttons {
    flex-direction: column;
  }
  
  .btn {
    width: 100%;
    text-align: center;
  }
}
</style>