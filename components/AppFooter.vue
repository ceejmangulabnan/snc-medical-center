<template>
  <v-footer padless class="footer">
    <v-container class="pt-10 pb-4">
      <v-row class="footer-top" dense>
        <v-col cols="12" md="6" lg="3" class="mb-6 footer-group">
          <h4 class="footer-heading">SNC Medical Center</h4>
          <p class="footer-text">
            Providing specialized, patient-centered care with a focus on quality, compassion, and expertise.
          </p>
        </v-col>

        <v-col cols="12" md="6" lg="3" class="mb-6 footer-group">
          <h4 class="footer-heading">Quick Links</h4>
          <ul class="footer-list">
            <li><router-link to="/">Home</router-link></li>
            <li><router-link to="/">About Us</router-link></li>
            <li><router-link to="/">Doctors / Specialists</router-link></li>
            <li><router-link to="/">Services</router-link></li>
            <li><router-link to="/">Contact</router-link></li>
            <li><router-link to="/">Book Appointment</router-link></li>
          </ul>
        </v-col>

        <v-col cols="12" md="6" lg="3" class="mb-6 footer-group">
          <h4 class="footer-heading">Legal</h4>
          <ul class="footer-list">
            <li><router-link to="/privacy-policy">Privacy Policy</router-link></li>
            <li><router-link to="/terms">Terms of Service</router-link></li>
          </ul>
        </v-col>

        <v-col cols="12" md="6" lg="3" class="mb-6 footer-group">
          <h4 class="footer-heading">Social</h4>
          <div class="footer-social">
            <a href="#" aria-label="Facebook"><v-icon small>mdi-facebook</v-icon></a>
            <a href="#" aria-label="Instagram"><v-icon small>mdi-instagram</v-icon></a>
            <a href="#" aria-label="Twitter"><v-icon small>mdi-twitter</v-icon></a>
            <a href="#" aria-label="YouTube"><v-icon small>mdi-youtube</v-icon></a>
            <a href="#" aria-label="WordPress"><v-icon small>mdi-wordpress</v-icon></a>
          </div>
        </v-col>
      </v-row>

      <v-divider class="my-6"></v-divider>

      <p class="footer-copy text-center text-caption">
        © 2025 SNC Medical Center | All Rights Reserved
      </p>
    </v-container>
  </v-footer>
</template>

<script>
export default {
  name: 'AppFooter'
}
</script>

<style scoped>
.footer {
  background-color: white;
  color: #333;
}

.footer-heading {
  font-weight: bold;
  margin-bottom: 0.75rem;
}

.footer-text {
  font-size: 0.9rem;
  line-height: 1.5;
  color: #666;
}

.footer-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-list li {
  margin-bottom: 0.5rem;
}

.footer-list a {
  text-decoration: none;
  color: inherit;
  font-size: 0.9rem;
}

.footer-list a:hover {
  text-decoration: underline;
}

.footer-social {
  display: flex;
  gap: 0.75rem;
  align-items: center;
  color: #000022;
}

.footer-social a {
  color: inherit;
}

.footer-copy {
  color: #777;
}

.footer-group {
  padding: 0 2rem;
}
</style>
