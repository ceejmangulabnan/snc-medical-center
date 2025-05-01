<template>
  <v-app-bar class="navbar primary" floating dense>
    <NuxtLink class="unstyled" to="/">SNC Medical Center</NuxtLink>
  </v-app-bar>
</template>

<style>
.unstyled {
  text-decoration: none;
  color: white !important;
  font-weight: 700;
}

.navbar {
  color: white;
  z-index: 999;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
}
</style>
