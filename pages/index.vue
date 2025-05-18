<template>
  <main>
    <section class="hero mb-4 mb-md-10">
      <div class="hero-text">
        <h1 class="text-h4 text-sm-h3 text-md-h2 text-lg-h1 font-weight-medium">SNC Medical Center</h1>
        <p class="text-subtitle text-md-h6 font-italic font-weight-regular" style="color: #F8F8F8;">Specialized care,
          personalized for you.</p>
      </div>
      <div class="d-flex flex-column d-sm-flex flex-sm-row gap">
        <v-btn elevation="4" raised rounded :small="isMobile" class="button">
          Get Started
        </v-btn>
        <v-btn elevation="4" raised rounded :small="isMobile" class="button inverted">Book a Consultation</v-btn>
      </div>
    </section>
    <section class="specialization px-4">
      <div class="specialization py-8">
        <h2 class="text-h4 text-sm-h3 font-weight-bold mb-4 text-center">Meet Our Specialists</h2>
        <p class="text-center" style="color: #585858;">Meet the doctors behind our care—respected specialists who bring
          years of training,
          expertise, and leadership
          in their fields.</p>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'Home',
  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.smAndDown
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

@media only screen and (max-width: 600px) {
  .gap {
    gap: 0.5rem;
  }
}
</style>
