<template>
  <main>
    <section class="hero pb-4 pb-md-10">
      <div class="hero-text">
        <h1 class="text-h4 text-sm-h3 text-md-h2 text-lg-h1 font-weight-medium">SNC Medical Center</h1>
        <p class="text-subtitle text-md-h6 font-italic font-weight-regular" style="color: #F8F8F8;">
          Specialized care, personalized for you.
        </p>
      </div>

      <div class="d-flex flex-column d-sm-flex flex-sm-row gap">
        <v-btn @click="openLogin" elevation="4" raised rounded :small="isMobile" class="button">
          Get Started
        </v-btn>
        <v-btn @click="openLogin" elevation="4" raised rounded :small="isMobile" class="button inverted">
          Book a Consultation
        </v-btn>

        <!-- Login Modal -->
        <LoginModal v-model="showLogin" @login-success="onLoginSuccess" />
      </div>
    </section>

    <section class="specialization px-4 py-10">
      <div class="specialization py-8">
        <h2 class="text-h4 text-sm-h3 font-weight-bold mb-4 text-center">Meet Our Specialists</h2>
        <p class="text-center" style="color: #585858;">
          Meet the doctors behind our care—respected specialists who bring years of training, expertise, and leadership
          in their fields.
        </p>
      </div>

      <div class="doctor-grid px-4">
        <v-card v-for="doctor in doctors" :key="doctor.name" class="doctor-card" elevated>
          <div>
            <router-link :to="`/${doctor.href}`" class="doctor-name-link">
              <h3>{{ doctor.name }}</h3>
            </router-link>
            <p>{{ doctor.title }}</p>
            <p>{{ doctor.bio }}</p>
          </div>
          <div class="spacer" />
          <v-btn :to="`/${doctor.href}`" small>View Profile</v-btn>
        </v-card>
      </div>
    </section>
  </main>
</template>

<script>
import LoginModal from '@/components/LoginModal.vue'

export default {
  name: 'Home',
  components: { LoginModal },

  data() {
    return {
      doctors: [],
      showLogin: false,
      isLoggedIn: false
    }
  },

  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.smAndDown
    }
  },

  mounted() {
    this.isLoggedIn = localStorage.getItem('isLoggedIn') === 'true'
    this.loadDoctors()
  },

  methods: {
    async loadDoctors() {
      try {
        const res = await fetch('/doctors.json')
        this.doctors = await res.json()
      } catch (err) {
        console.error('Failed to load doctors.json:', err)
        this.doctors = []
      }
    },

    openLogin() {
      if (this.isLoggedIn) return
      this.showLogin = true
    },

    onLoginSuccess() {
      this.showLogin = false
      this.isLoggedIn = true
      localStorage.setItem('isLoggedIn', 'true')
      location.reload()
    },

    logout() {
      this.isLoggedIn = false
      localStorage.removeItem('isLoggedIn')
    }
  }
}
</script>

<style scoped>
.hero {
  min-height: 100vh;
  background-image: url('../assets/hero-image.webp');
  background-size: cover;
  background-position: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
  text-align: center;
  padding: 0 1rem;
}

.hero-text {
  color: white;
  z-index: 2;
  position: relative;
}

.specialization {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.gap {
  gap: 1rem;
}

.doctor-card {
  display: flex;
  flex-direction: column;
  padding: 1rem 2rem;
  border-radius: 0.5rem;
  height: 100%;
}

.spacer {
  flex-grow: 1;
}

.doctor-name-link h3 {
  margin: 0;
  transition: color 0.2s ease;
  color: inherit;
  text-decoration: none;
  cursor: pointer;
}

.doctor-name-link {
  flex-grow: 1;
  color: #000022;
  text-decoration: none;
}

.doctor-name-link:hover h3 {
  color: #000080;
}

.doctor-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
  max-width: 1400px;
}

@media (min-width: 768px) {
  .doctor-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media only screen and (max-width: 600px) {
  .gap {
    gap: 0.5rem;
  }
}
</style>
