<template>
  <v-row justify="center" align="center">
    <v-col class="hero">
      <div class="hero-text">
        <h1 class="display-1 font-weight-bold">SNC Medical Center</h1>
        <p>Specialized care, personalized for you.</p>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'Home',
}
</script>

<style>
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.hero-text {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
