<script setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-brand">
          <a href="#" class="footer-logo">Work<span>Net</span></a>
          <p>Empowering businesses with superior network solutions since 2010. We design, implement, and manage secure and scalable networks for companies of all sizes.</p>
        </div>
        
        <div class="footer-links">
          <div class="footer-column">
            <h3>Services</h3>
            <ul>
              <li><a href="#services">Network Security</a></li>
              <li><a href="#services">Wireless Solutions</a></li>
              <li><a href="#services">Cloud Integration</a></li>
              <li><a href="#services">Network Management</a></li>
              <li><a href="#services">VoIP Systems</a></li>
            </ul>
          </div>
          
          <div class="footer-column">
            <h3>Company</h3>
            <ul>
              <li><a href="#about">About Us</a></li>
              <li><a href="#testimonials">Testimonials</a></li>
              <li><a href="#">Careers</a></li>
              <li><a href="#">Partners</a></li>
              <li><a href="#">Blog</a></li>
            </ul>
          </div>
          
          <div class="footer-column">
            <h3>Support</h3>
            <ul>
              <li><a href="#contact">Contact Us</a></li>
              <li><a href="#">Help Center</a></li>
              <li><a href="#">FAQ</a></li>
              <li><a href="#">Service Status</a></li>
              <li><a href="#">Terms of Service</a></li>
            </ul>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; {{ currentYear }} WorkNet. All rights reserved.</p>
        <div class="footer-social">
          <a href="#" aria-label="LinkedIn">
            <span class="social-icon">in</span>
          </a>
          <a href="#" aria-label="Twitter">
            <span class="social-icon">𝕏</span>
          </a>
          <a href="#" aria-label="Facebook">
            <span class="social-icon">f</span>
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: #18181a;
  padding: 5rem 0 2rem;
  color: #c0c0c0;
}

.footer-content {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 4rem;
  margin-bottom: 3rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  padding-bottom: 3rem;
}

.footer-brand {
  max-width: 350px;
}

.footer-logo {
  font-size: 1.8rem;
  font-weight: 700;
  color: #ffffff;
  text-decoration: none;
  margin-bottom: 1.5rem;
  display: inline-block;
  letter-spacing: -0.5px;
}

.footer-logo span {
  color: #8a2be2;
}

.footer-brand p {
  font-size: 0.95rem;
  line-height: 1.7;
  margin-top: 1rem;
}

.footer-links {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.footer-column h3 {
  font-size: 1.1rem;
  color: #ffffff;
  margin-bottom: 1.5rem;
  font-weight: 600;
  position: relative;
}

.footer-column h3::after {
  content: '';
  position: absolute;
  width: 30px;
  height: 2px;
  background-color: #8a2be2;
  bottom: -10px;
  left: 0;
}

.footer-column ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-column li {
  margin-bottom: 0.8rem;
}

.footer-column a {
  color: #c0c0c0;
  text-decoration: none;
  transition: color 0.3s ease;
  font-size: 0.95rem;
}

.footer-column a:hover {
  color: #ffffff;
}

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 2rem;
}

.footer-bottom p {
  font-size: 0.9rem;
}

.footer-social {
  display: flex;
  gap: 1rem;
}

.footer-social a {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  color: #ffffff;
  text-decoration: none;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.social-icon {
  font-size: 1.1rem;
  font-weight: 600;
}

.footer-social a:hover {
  background-color: #8a2be2;
  transform: translateY(-3px);
}

@media screen and (max-width: 1024px) {
  .footer-content {
    gap: 2rem;
  }
}

@media screen and (max-width: 768px) {
  .footer {
    padding: 3rem 0 2rem;
  }
  
  .footer-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  
  .footer-brand {
    max-width: 100%;
  }
  
  .footer-links {
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }
}

@media screen and (max-width: 480px) {
  .footer-links {
    grid-template-columns: 1fr;
  }
  
  .footer-bottom {
    flex-direction: column;
    gap: 1.5rem;
    text-align: center;
  }
}
</style>