<template>
  <main>
    <section class="hero">
      <div class="hero-text">
        <h1 class="text-h4 text-sm-h3 text-md-h2 text-lg-h1 font-weight-medium">SNC Medical Center</h1>
        <p class="text-subtitle text-md-h6 font-italic font-weight-regular">Specialized care, personalized for you.</p>
      </div>
    </section>
    <section class="specialization">
    </section>
  </main>
</template>

<script>
export default {
  name: 'Home',
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
}

.hero-text {
  color: white;
  z-index: 2;
  position: relative;
}

.specialization {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
