<script setup>
import { ref } from 'vue';

const formData = ref({
  name: '',
  email: '',
  phone: '',
  company: '',
  message: ''
});

const isSubmitting = ref(false);
const submitSuccess = ref(false);
const submitError = ref(false);

const handleSubmit = (e) => {
  e.preventDefault();
  isSubmitting.value = true;
  
  // Simulate form submission
  setTimeout(() => {
    isSubmitting.value = false;
    submitSuccess.value = true;
    
    // Reset form data
    formData.value = {
      name: '',
      email: '',
      phone: '',
      company: '',
      message: ''
    };
    
    // Reset success message after 5 seconds
    setTimeout(() => {
      submitSuccess.value = false;
    }, 5000);
  }, 1500);
};
</script>

<template>
  <section id="contact" class="contact">
    <div class="container">
      <div class="contact-wrapper">
        <div class="contact-info">
          <h2>Get in Touch</h2>
          <p>Ready to transform your network infrastructure? Contact us today for a free consultation and let our experts help you build a reliable, secure, and scalable network solution.</p>
          
          <div class="contact-methods">
            <div class="contact-method">
              <div class="method-icon">📞</div>
              <div class="method-details">
                <h3>Call Us</h3>
                <p>(555) 123-4567</p>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">✉️</div>
              <div class="method-details">
                <h3>Email Us</h3>
                <p>info@worknet.com</p>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">🏢</div>
              <div class="method-details">
                <h3>Visit Us</h3>
                <p>123 Tech Avenue, Suite 500<br>San Francisco, CA 94105</p>
              </div>
            </div>
          </div>
        </div>
        
        <div class="contact-form-container">
          <form @submit="handleSubmit" class="contact-form">
            <div class="form-header">
              <h3>Request a Consultation</h3>
              <p>Fill out the form below and our team will get back to you within 24 hours.</p>
            </div>
            
            <div class="form-group">
              <label for="name">Full Name</label>
              <input 
                type="text" 
                id="name" 
                v-model="formData.name" 
                required 
                placeholder="Your name"
              >
            </div>
            
            <div class="form-row">
              <div class="form-group">
                <label for="email">Email</label>
                <input 
                  type="email" 
                  id="email" 
                  v-model="formData.email" 
                  required 
                  placeholder="your@email.com"
                >
              </div>
              
              <div class="form-group">
                <label for="phone">Phone Number</label>
                <input 
                  type="tel" 
                  id="phone" 
                  v-model="formData.phone" 
                  placeholder="(555) 123-4567"
                >
              </div>
            </div>
            
            <div class="form-group">
              <label for="company">Company</label>
              <input 
                type="text" 
                id="company" 
                v-model="formData.company" 
                placeholder="Your company name"
              >
            </div>
            
            <div class="form-group">
              <label for="message">How Can We Help?</label>
              <textarea 
                id="message" 
                v-model="formData.message" 
                required 
                rows="4" 
                placeholder="Tell us about your network needs..."
              ></textarea>
            </div>
            
            <button 
              type="submit" 
              class="submit-btn" 
              :disabled="isSubmitting"
            >
              <span v-if="!isSubmitting">Send Message</span>
              <span v-else>Sending...</span>
            </button>
            
            <div v-if="submitSuccess" class="success-message">
              Your message has been sent successfully! We'll be in touch soon.
            </div>
            
            <div v-if="submitError" class="error-message">
              Something went wrong. Please try again later.
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact {
  padding: 6rem 0;
  background-color: #2c2c2e;
  position: relative;
  overflow: hidden;
}

.contact::before {
  content: '';
  position: absolute;
  top: -200px;
  left: -200px;
  width: 400px;
  height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(66, 190, 114, 0.05) 0%, rgba(66, 190, 114, 0) 70%);
  z-index: 1;
}

.contact-wrapper {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 4rem;
  position: relative;
  z-index: 2;
}

.contact-info h2 {
  font-size: 2.5rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 1.5rem;
  position: relative;
}

.contact-info h2::after {
  content: '';
  position: absolute;
  width: 60px;
  height: 3px;
  background-color: #8a2be2;
  bottom: -15px;
  left: 0;
}

.contact-info p {
  font-size: 1.1rem;
  line-height: 1.7;
  color: #d0d0d0;
  margin-bottom: 2.5rem;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.contact-method {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}

.method-icon {
  font-size: 1.5rem;
  background: rgba(138, 43, 226, 0.1);
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 10px;
}

.method-details h3 {
  font-size: 1.1rem;
  font-weight: 600;
  color: #ffffff;
  margin-bottom: 0.3rem;
}

.method-details p {
  font-size: 1rem;
  color: #c0c0c0;
  margin-bottom: 0;
}

.contact-form-container {
  background: linear-gradient(145deg, #22222a, #2c2c34);
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
}

.contact-form {
  padding: 2.5rem;
}

.form-header {
  margin-bottom: 2rem;
  text-align: center;
}

.form-header h3 {
  font-size: 1.5rem;
  font-weight: 600;
  color: #ffffff;
  margin-bottom: 0.5rem;
}

.form-header p {
  font-size: 0.95rem;
  color: #c0c0c0;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

label {
  display: block;
  font-size: 0.9rem;
  font-weight: 500;
  color: #e0e0e0;
  margin-bottom: 0.5rem;
}

input, textarea {
  width: 100%;
  padding: 0.8rem 1rem;
  font-size: 1rem;
  background-color: rgba(28, 28, 30, 0.5);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 8px;
  color: #ffffff;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
}

input:focus, textarea:focus {
  outline: none;
  border-color: #8a2be2;
  box-shadow: 0 0 0 2px rgba(138, 43, 226, 0.2);
}

textarea {
  resize: vertical;
}

input::placeholder, textarea::placeholder {
  color: rgba(255, 255, 255, 0.4);
}

.submit-btn {
  width: 100%;
  padding: 1rem;
  background: linear-gradient(135deg, #8a2be2 0%, #42be72 100%);
  border: none;
  border-radius: 8px;
  color: #ffffff;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: transform 0.3s ease, opacity 0.3s ease;
}

.submit-btn:hover {
  transform: translateY(-2px);
}

.submit-btn:active {
  transform: translateY(0);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.success-message {
  margin-top: 1.5rem;
  padding: 1rem;
  background-color: rgba(66, 190, 114, 0.1);
  border: 1px solid rgba(66, 190, 114, 0.3);
  border-radius: 8px;
  color: #42be72;
  text-align: center;
}

.error-message {
  margin-top: 1.5rem;
  padding: 1rem;
  background-color: rgba(255, 69, 58, 0.1);
  border: 1px solid rgba(255, 69, 58, 0.3);
  border-radius: 8px;
  color: #ff453a;
  text-align: center;
}

@media screen and (max-width: 1024px) {
  .contact-wrapper {
    gap: 2rem;
  }
}

@media screen and (max-width: 768px) {
  .contact {
    padding: 4rem 0;
  }
  
  .contact-wrapper {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  
  .contact-info h2 {
    font-size: 2rem;
  }
  
  .contact-info p {
    font-size: 1rem;
  }
}

@media screen and (max-width: 480px) {
  .form-row {
    grid-template-columns: 1fr;
  }
  
  .contact-form {
    padding: 1.5rem;
  }
}
</style>