<template>
  <v-app-bar class="navbar" :elevation="hover ? 24 : 6" app dense flat>
    <NuxtLink class="unstyled" to="/">SNC Medical Center</NuxtLink>
  </v-app-bar>
</template>

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
