<script setup>
import { ref } from 'vue';

const services = ref([
  {
    icon: '🛡️',
    title: 'Network Security',
    description: 'Protect your network infrastructure with enterprise-grade security solutions including firewall management, intrusion detection and VPN services.'
  },
  {
    icon: '📡',
    title: 'Wireless Solutions',
    description: 'Design and implementation of wireless networks for businesses of all sizes, with seamless coverage and high-performance connectivity.'
  },
  {
    icon: '☁️',
    title: 'Cloud Integration',
    description: 'Seamlessly integrate your on-premises infrastructure with cloud services for improved scalability, backup and disaster recovery.'
  },
  {
    icon: '🔧',
    title: 'Network Management',
    description: 'Proactive network monitoring, maintenance and support to keep your business operations running efficiently and minimize downtime.'
  },
  {
    icon: '📞',
    title: 'VoIP Systems',
    description: 'Modern voice communication solutions that enhance collaboration while reducing costs compared to traditional phone systems.'
  },
  {
    icon: '💡',
    title: 'IT Consulting',
    description: 'Strategic technology planning and consultation to align your network infrastructure with your business goals and future growth.'
  }
]);
</script>

<template>
  <section id="services" class="services">
    <div class="container">
      <div class="section-header">
        <h2>Our Services</h2>
        <p>Comprehensive network solutions to power your business</p>
      </div>
      <div class="services-grid">
        <div v-for="(service, index) in services" :key="index" class="service-card">
          <div class="service-icon">{{ service.icon }}</div>
          <h3>{{ service.title }}</h3>
          <p>{{ service.description }}</p>
          <a href="#contact" class="service-link">Learn more <span>&rarr;</span></a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.services {
  padding: 6rem 0;
  background-color: #1c1c1e;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-header h2 {
  font-size: 2.5rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 1rem;
  position: relative;
  display: inline-block;
}

.section-header h2::after {
  content: '';
  position: absolute;
  width: 60px;
  height: 3px;
  background-color: #8a2be2;
  bottom: -15px;
  left: 50%;
  transform: translateX(-50%);
}

.section-header p {
  font-size: 1.2rem;
  color: #d0d0d0;
  max-width: 600px;
  margin: 0 auto;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
}

.service-card {
  background: linear-gradient(145deg, #22222a, #2c2c34);
  border-radius: 12px;
  padding: 2rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  position: relative;
  overflow: hidden;
  height: 100%;
  display: flex;
  flex-direction: column;
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.12);
}

.service-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.2);
}

.service-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 4px;
  height: 0;
  background: linear-gradient(180deg, #8a2be2, #42be72);
  transition: height 0.3s ease;
}

.service-card:hover::before {
  height: 100%;
}

.service-icon {
  font-size: 3rem;
  margin-bottom: 1.5rem;
  display: inline-block;
  filter: grayscale(0.2);
  transition: transform 0.3s ease, filter 0.3s ease;
}

.service-card:hover .service-icon {
  transform: scale(1.1);
  filter: grayscale(0);
}

.service-card h3 {
  font-size: 1.4rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: #ffffff;
}

.service-card p {
  font-size: 1rem;
  line-height: 1.6;
  color: #c0c0c0;
  margin-bottom: 1.5rem;
  flex-grow: 1;
}

.service-link {
  color: #8a2be2;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.95rem;
  display: inline-flex;
  align-items: center;
  transition: gap 0.3s ease;
  gap: 0.5rem;
}

.service-link:hover {
  gap: 0.8rem;
}

@media screen and (max-width: 768px) {
  .services {
    padding: 4rem 0;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
  
  .section-header p {
    font-size: 1.1rem;
  }
}

@media screen and (max-width: 480px) {
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .service-card {
    padding: 1.5rem;
  }
  
  .service-icon {
    font-size: 2.5rem;
  }
}
</style>