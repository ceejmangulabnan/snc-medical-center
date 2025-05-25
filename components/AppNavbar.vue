<template>
  <v-app-bar class="navbar" elevation="6" app dense flat>
    <NuxtLink class="unstyled" to="/">SNC Medical Center</NuxtLink>

    <v-spacer />

    <div class="d-flex gap">
      <v-btn to="/" text small>
        Home
      </v-btn>

      <!-- Specialists Dropdown -->
      <v-menu offset-y>
        <template #activator="{ on, attrs }">
          <v-btn v-bind="attrs" v-on="on" text small>
            Specialists
            <v-icon right>mdi-chevron-down</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item v-for="(doctor, index) in doctors" :key="index" :to="`/${doctor.href}`" link>
            <v-list-item-title>{{ doctor.specialty }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn v-if="!isLoggedIn" small color="primary" @click="loginDialog = true" class="ml-4">
        Login
      </v-btn>

      <v-btn v-else outlined small color="error" @click="logout" class="ml-4">
        Logout
      </v-btn>


    </div>
    <!-- Reusable Login Modal -->
    <LoginModal v-model="loginDialog" @login-success="onLoginSuccess" />
  </v-app-bar>
</template>

<script>
import LoginModal from '@/components/LoginModal.vue'

export default {
  components: {
    LoginModal
  },

  data() {
    return {
      loginDialog: false,
      isLoggedIn: false,
      doctors: []
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

    onLoginSuccess() {
      this.isLoggedIn = true
      localStorage.setItem('isLoggedIn', 'true')
      location.reload()
    },

    logout() {
      this.isLoggedIn = false
      localStorage.removeItem('isLoggedIn')
      location.reload()
    }
  }
}
</script>

<style scoped>
.gap {
  gap: 0.5rem;
}

.unstyled {
  text-decoration: none;
  color: #000022 !important;
  font-weight: 700;
}

.navbar {
  background-color: white !important;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(8px);
  padding: 0 1rem;
  position: fixed;
  z-index: 999;
}
</style>
