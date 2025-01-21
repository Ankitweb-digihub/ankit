<template>

  <div id="app">
    <!-- Navigation Bar -->
    <nav class="navbar">
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#portfolio">Portfolio</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
      <h1>Welcome to Our Website</h1>
      <p>Your one-stop solution for everything!</p>
      <button @click="scrollToSection('about')">Learn More</button>
    </section>

    <!-- About Section -->
    <section id="about" class="section about-section">
      <div class="about-content">
        <div class="about-text">
          <h2>About Us</h2>
          <p>We are a passionate team committed to delivering innovative solutions to help your business grow. We specialize in web development, design, and digital marketing to ensure your business stays ahead in today's competitive market.</p>
        </div>
        <div class="about-image">
          <img src="assets/images/campaign-creators-iEiUITs149M-unsplash.jpg" alt="About Us" />
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="section services-section">
      <h2>Our Services</h2>
      <p>We offer a wide range of high-quality services to meet your needs:</p>
      <div class="services-grid">
        <div class="service">
          <img src="https://img.icons8.com/ios/452/maintenance.png" alt="Web Development">
          <h3>Web Development</h3>
          <p>Build modern, responsive, and high-performance websites tailored to your needs.</p>
        </div>
        <div class="service">
          <img src="https://img.icons8.com/ios/452/maintenance.png" alt="Web Development">
          <h3>Web Development</h3>
          <p>Build modern, responsive, and high-performance websites tailored to your needs.</p>
        </div>
        <div class="service">
          <img src="https://img.icons8.com/ios/452/idea.png" alt="UI/UX Design">
          <h3>UI/UX Design</h3>
          <p>Create beautiful and user-friendly interfaces that enhance user experience.</p>
        </div>
        <div class="service">
          <img src="https://img.icons8.com/ios/452/maintenance.png" alt="Digital Marketing">
          <h3>Digital Marketing</h3>
          <p>Increase your brand's visibility and reach your audience with targeted marketing strategies.</p>
        </div>
        <div class="service">
          <img src="https://img.icons8.com/ios/452/cloud-storage.png" alt="Cloud Services">
          <h3>Cloud Services</h3>
          <p>Ensure your business runs smoothly with secure and reliable cloud solutions.</p>
        </div>
      </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio" class="section portfolio-section">
      <h2>Our Portfolio</h2>
      <p>Here are some of the projects we’ve worked on:</p>

      <!-- Portfolio Grid -->
      <div class="portfolio-grid">
        <div class="portfolio-item">
          <img src="assets/images/guilherme-vasconcelos-VVBD_bjk7c8-unsplash.jpg" alt="Project 1">
          <h3>Project One</h3>
          <p>A description of the project goes here. It could be a website, application, or branding project.</p>
        </div>
        <div class="portfolio-item">
          <img src="assets/images/rubaitul-azad-Umpjhyb4iIk-unsplash.jpg" alt="Project 1">
          <h3>Project One</h3>
          <p>A description of the project goes here. It could be a website, application, or branding project.</p>
        </div>
        <div class="portfolio-item">
          <img src="assets/images/rubaitul-azad-368KQaBgon8-unsplash.jpg" alt="Project 2">
          <h3>Project Two</h3>
          <p>A description of the project goes here. It could be a website, application, or branding project.</p>
        </div>
        <div class="portfolio-item">
          <img src="assets/images/rubaitul-azad-368KQaBgon8-unsplash.jpg" alt="Project 3">
          <h3>Project Three</h3>
          <p>A description of the project goes here. It could be a website, application, or branding project.</p>
        </div>
        <div class="portfolio-item">
          <img src="assets/images/rubaitul-azad-N0gLp-w6zF4-unsplash.jpg" alt="Project 4">
          <h3>Project Four</h3>
          <p>A description of the project goes here. It could be a website, application, or branding project.</p>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section contact-section">
      <h2>Contact Us</h2>
      <p>If you have any questions or would like to get in touch, please fill out the form below:</p>

      <!-- Contact Form -->
      <form @submit.prevent="submitForm" class="contact-form">
        <div class="form-group">
          <label for="name">Your Name:</label>
          <input type="text" id="name" v-model="form.name" required />
        </div>

        <div class="form-group">
          <label for="email">Your Email:</label>
          <input type="email" id="email" v-model="form.email" required />
        </div>

        <div class="form-group">
          <label for="message">Your Message:</label>
          <textarea id="message" v-model="form.message" required></textarea>
        </div>

        <button type="submit">Submit</button>
      </form>

      <!-- Confirmation Message -->
      <div v-if="formSubmitted" class="confirmation-message">
        <p>Thank you for contacting us! We will get back to you soon.</p>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="footer-content">
        <p>&copy; 2025 Digihub. All Rights Reserved.</p>
        <ul class="footer-links">
          <li><a href="#privacy-policy">Privacy Policy</a></li>
          <li><a href="#terms-of-service">Terms of Service</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </footer>
  </div>
  
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      },
      formSubmitted: false
    };
  },
  methods: {
    scrollToSection(sectionId) {
      const section = document.getElementById(sectionId);
      if (section) {
        window.scrollTo({
          top: section.offsetTop,
          behavior: 'smooth',
        });
      }
    },
    submitForm() {
      // Show confirmation message after form submission
      this.formSubmitted = true;

      // Reset the form fields after submission
      this.form.name = '';
      this.form.email = '';
      this.form.message = '';
    }
  }
}
</script>

<style scoped>
/* Basic Styles for Layout */
#app {
  font-family: Arial, sans-serif;
  color: #333;
  background-color: #f9f9f9;
}

.navbar {
  background-color: #333;
  color: white;
  padding: 10px;
  position: sticky;
  top: 0;
  z-index: 100;
}

.navbar ul {
  list-style-type: none;
  padding: 0;
  text-align: center;
}

.navbar li {
  display: inline;
  margin: 0 15px;
}

.navbar a {
  color: white;
  text-decoration: none;
  font-size: 18px;
}

.hero {
  background-image:url("assets/images/abstract-digital-grid-black-background.jpg");
  color: white;
  padding: 80px 20px;
  text-align: center;
}

.hero h1 {
  font-size: 3em;
}

.hero p {
  font-size: 1.2em;
}

button {
  background-color: white;
  color: #4CAF50;
  font-size: 16px;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}

.section {
  padding: 50px 20px;
  text-align: center;
}

/* About Section Styles */
.about-section {
  background-color: #f4f4f4;
}

.about-content {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: row;
  gap: 30px;
  text-align: left;
}

.about-text {
  max-width: 600px;
}

.about-image img {
  width: 100%;
  max-width: 400px;
  border-radius: 10px;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 30px;
  padding-top: 30px;
}

.service {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 20px;
  text-align: center;
}

.service img {
  width: 60px;
  height: 60px;
  margin-bottom: 15px;
}

.service h3 {
  font-size: 1.5em;
  color: #333;
}

.service p {
  font-size: 1em;
  color: #666;
}

/* Portfolio Section Styles */
.portfolio-section {
  background-color: #f4f4f4;
}

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 30px;
  padding-top: 30px;
}

.portfolio-item {
  background-color: white;
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.portfolio-item img {
  width: 100%;
  height: auto;
  border-radius: 10px;
}

.portfolio-item h3 {
  margin-top: 15px;
  font-size: 1.3em;
}

.portfolio-item p {
  color: #666;
  font-size: 1em;
}

/* Contact Section Styles */
.contact-section {
  background-color: #f4f4f4;
}

.contact-form {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 600px;
  margin: 0 auto;
  gap: 20px;
}

.contact-form .form-group {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.contact-form label {
  font-weight: bold;
  margin-bottom: 8px;
}

.contact-form input,
.contact-form textarea {
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ddd;
  width: 100%;
  font-size: 16px;
}

.contact-form button {
  background-color: #4CAF50;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}

.contact-form button:hover {
  background-color: #45a049;
}

.confirmation-message {
  text-align: center;
  font-size: 18px;
  color: #4CAF50;
  margin-top: 20px;
}

/* Footer Styles */
.footer {
  background-color: #333;
  color: white;
  padding: 20px 0;
  text-align: center;
}

.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.footer p {
  font-size: 14px;
}

.footer-links {
  list-style-type: none;
  padding: 0;
  margin-top: 10px;
}

.footer-links li {
  display: inline;
  margin: 0 10px;
}

.footer-links a {
  color: white;
  text-decoration: none;
}

.footer-links a:hover {
  text-decoration: underline;
}
</style>

