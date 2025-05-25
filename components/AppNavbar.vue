<template>
  <v-app-bar class="navbar" elevation="6" app dense flat>
    <NuxtLink class="unstyled" to="/">SNC Medical Center</NuxtLink>

    <v-spacer />

    <v-btn v-if="!isLoggedIn" small color="primary" @click="loginDialog = true">
      Login
    </v-btn>

    <v-btn v-else outlined small color="error" @click="logout">
      Logout
    </v-btn>

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
      isLoggedIn: false
    }
  },

  mounted() {
    this.isLoggedIn = localStorage.getItem('isLoggedIn') === 'true'
  },

  methods: {
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
