<script setup>
import { ref, onMounted } from 'vue';

const testimonials = ref([
  {
    quote: "WorkNet completely transformed our IT infrastructure with their network solutions. Our productivity has increased by 30% and downtime is virtually non-existent.",
    author: "Sarah Johnson",
    position: "CTO, Innovative Solutions"
  },
  {
    quote: "We've been working with WorkNet for over 5 years now. Their network security services have protected us from multiple potential breaches and their support team is always responsive.",
    author: "Michael Chen",
    position: "IT Director, Global Finance"
  },
  {
    quote: "The cloud integration services provided by WorkNet helped us seamlessly transition to a hybrid work model. Their expertise made what seemed like a daunting process incredibly smooth.",
    author: "Emily Rodriguez",
    position: "Operations Manager, TechStart"
  },
  {
    quote: "Their network engineers are top-notch professionals who understand our business needs and provide solutions that are both effective and cost-efficient.",
    author: "David Williams",
    position: "CEO, Nexus Enterprises"
  }
]);

const currentIndex = ref(0);
const testimonialInterval = ref(null);

const nextTestimonial = () => {
  currentIndex.value = (currentIndex.value + 1) % testimonials.value.length;
};

const prevTestimonial = () => {
  currentIndex.value = (currentIndex.value - 1 + testimonials.value.length) % testimonials.value.length;
};

const startAutoSlide = () => {
  testimonialInterval.value = setInterval(() => {
    nextTestimonial();
  }, 5000);
};

const stopAutoSlide = () => {
  clearInterval(testimonialInterval.value);
};

onMounted(() => {
  startAutoSlide();
});
</script>

<template>
  <section id="testimonials" class="testimonials">
    <div class="container">
      <div class="section-header">
        <h2>What Our Clients Say</h2>
        <p>Trusted by businesses across industries</p>
      </div>
      <div class="testimonial-slider" @mouseenter="stopAutoSlide" @mouseleave="startAutoSlide">
        <div class="testimonial-container">
          <div class="testimonial-track" :style="`transform: translateX(-${currentIndex * 100}%)`">
            <div v-for="(testimonial, index) in testimonials" :key="index" class="testimonial-card">
              <div class="quote-icon">"</div>
              <p class="quote">{{ testimonial.quote }}</p>
              <div class="author-info">
                <p class="author-name">{{ testimonial.author }}</p>
                <p class="author-position">{{ testimonial.position }}</p>
              </div>
            </div>
          </div>
        </div>
        <div class="controls">
          <button @click="prevTestimonial" class="control-btn prev-btn">
            <span>&larr;</span>
          </button>
          <div class="indicators">
            <span 
              v-for="(_, index) in testimonials" 
              :key="index" 
              :class="{ active: index === currentIndex }"
              @click="currentIndex = index"
            ></span>
          </div>
          <button @click="nextTestimonial" class="control-btn next-btn">
            <span>&rarr;</span>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.testimonials {
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

.testimonial-slider {
  max-width: 900px;
  margin: 0 auto;
  position: relative;
}

.testimonial-container {
  overflow: hidden;
  margin-bottom: 2rem;
}

.testimonial-track {
  display: flex;
  transition: transform 0.5s ease;
}

.testimonial-card {
  flex: 0 0 100%;
  background: linear-gradient(145deg, #22222a, #2c2c34);
  border-radius: 12px;
  padding: 3rem;
  position: relative;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
}

.quote-icon {
  font-size: 5rem;
  position: absolute;
  top: 20px;
  left: 20px;
  font-family: 'Times New Roman', serif;
  color: rgba(138, 43, 226, 0.1);
  line-height: 1;
}

.quote {
  font-size: 1.2rem;
  line-height: 1.8;
  color: #e0e0e0;
  margin-bottom: 2rem;
  position: relative;
  z-index: 2;
  font-style: italic;
}

.author-info {
  text-align: right;
}

.author-name {
  font-size: 1.1rem;
  font-weight: 600;
  color: #ffffff;
  margin-bottom: 0.3rem;
}

.author-position {
  font-size: 0.9rem;
  color: #8a2be2;
}

.controls {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
}

.control-btn {
  background: none;
  border: none;
  font-size: 1.5rem;
  color: #8a2be2;
  cursor: pointer;
  transition: color 0.3s ease;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  background-color: rgba(138, 43, 226, 0.1);
}

.control-btn:hover {
  color: #ffffff;
  background-color: rgba(138, 43, 226, 0.3);
}

.indicators {
  display: flex;
  gap: 0.5rem;
}

.indicators span {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background-color: rgba(138, 43, 226, 0.3);
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.indicators span.active {
  background-color: #8a2be2;
  transform: scale(1.2);
}

@media screen and (max-width: 768px) {
  .testimonials {
    padding: 4rem 0;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
  
  .testimonial-card {
    padding: 2rem;
  }
  
  .quote {
    font-size: 1.1rem;
  }
}

@media screen and (max-width: 480px) {
  .testimonial-card {
    padding: 1.5rem;
  }
  
  .quote-icon {
    font-size: 3rem;
  }
  
  .quote {
    font-size: 1rem;
  }
  
  .controls {
    gap: 1rem;
  }
}
</style>