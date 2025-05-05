<template>
  <v-app-bar class="navbar" floating dense>
    <NuxtLink class="unstyled" to="/">SNC Medical Center</NuxtLink>
  </v-app-bar>
</template>

<style>
.unstyled {
  text-decoration: none;
  color: #000022 !important;
  font-weight: 700;
}

.navbar {
  background-color: white;
  z-index: 999;
  position: fixed;
  top: 10;
  left: 10;
  right: 10;
}
</style>
