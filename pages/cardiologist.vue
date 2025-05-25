<template>
  <main class="main">
    <header class="profile-header">
      <span class="title-sub">Attending Cardiologist</span>
      <h1 class="title-main">Dr. Cheljee Mangulabnan</h1>
      <p class="subtitle">
        Dr. Cheljee focuses on diagnosing and treating heart conditions. With a strong background in cardiovascular
        medicine, she provides expert care in managing heart disease and supporting patient recovery.
      </p>
    </header>

    <section class="section">
      <h2 class="section-title">About Dr. Cheljee</h2>
      <p class="section-text">
        Dr. Cheljee Mangulabnan is a board-certified cardiologist with several years of experience managing
        both acute and chronic cardiovascular conditions. She is dedicated to delivering compassionate,
        personalized care to every patient, using the latest diagnostic tools and treatment methods.
      </p>
    </section>

    <section class="section">
      <h2 class="section-title">Services Offered</h2>
      <ul class="service-list">
        <li>Heart disease diagnosis and treatment</li>
        <li>Hypertension management</li>
        <li>Cholesterol and lipid management</li>
        <li>Electrocardiogram (ECG/EKG) analysis</li>
        <li>Stress testing and heart imaging</li>
        <li>Post-heart attack care and rehabilitation</li>
        <li>Heart failure management</li>
        <li>Preventive cardiology and lifestyle counseling</li>
      </ul>
    </section>

    <section class="section">
      <h2 class="section-title">Approach to Care</h2>
      <p class="section-text">
        Dr. Cheljee takes a patient-first approach, focusing on education, open communication,
        and long-term wellness. She works closely with each individual to create a treatment plan
        tailored to their specific health needs and goals.
      </p>
    </section>
  </main>
</template>

<style scoped>
.main {
  background-color: #000040;
  color: white;
  min-height: 100vh;
  padding: 3rem 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.profile-header {
  text-align: center;
  max-width: 900px;
  margin-bottom: 3rem;
}

.title-sub {
  font-size: 1.2rem;
  font-style: italic;
  font-weight: 300;
  display: block;
  margin-bottom: 0.5rem;
  color: #bbbbff;
}

.title-main {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.subtitle {
  font-size: 1.1rem;
  font-weight: 300;
  color: #e0e0ff;
  line-height: 1.6;
}

.section {
  max-width: 800px;
  width: 100%;
  margin-bottom: 2.5rem;
  padding: 1rem;
  background-color: rgba(255, 255, 255, 0.05);
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
}

.section-title {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 1rem;
  border-bottom: 1px solid #8888aa;
  padding-bottom: 0.5rem;
}

.section-text {
  font-size: 1rem;
  color: #ddddff;
  line-height: 1.7;
}

.service-list {
  list-style: inside disc;
  padding-left: 0;
  color: #ddddff;
  font-size: 1rem;
  line-height: 1.6;
}

@media (min-width: 768px) {
  .title-main {
    font-size: 3rem;
  }

  .subtitle {
    font-size: 1.2rem;
  }

  .section-title {
    font-size: 1.75rem;
  }

  .section-text,
  .service-list {
    font-size: 1.05rem;
  }
}
</style>
