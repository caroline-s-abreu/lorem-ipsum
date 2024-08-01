<template>
  <section class="hero">
    <div class="hero-content">
      <div class="hero-text">
        <p class="hero-launch">BREVE LANÇAMENTO</p>
        <h1>Chegou a sua vez de viver bem.</h1>
        <p class="hero-subtitle">Lotes de 000 m², próximos ao shopping.</p>
        <p class="hero-description">
          The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those
          interested. Sections 1.10.32 and 1.10.33 from "de Finibus Bonorum et Malorum" by Cicero.
        </p>
      </div>
      <button>Quero conhecer</button>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HeroSection'
})
</script>

<style scoped lang="scss">
.hero {
  background-size: cover;
  background-image: url('../assets/headerImg.png');
  color: white;
  height: 555px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  .hero-content {
    display: flex;
    flex-direction: column;
    max-width: 1295px;
    align-items: flex-start;
    text-align: start;
    padding: 0 25px;
    gap: 2rem;
  }

  .hero-text {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    align-items: flex-start;
    padding: 32px 0;

    .hero-launch {
      font-size: 12px;
      font-weight: 700;
    }

    h1 {
      font-size: 32px;
      font-weight: 700;
    }

    .hero-subtitle {
      font-size: 20px;
      font-weight: 700;
    }

    .hero-description {
      font-size: 14px;
      font-weight: 400;
    }
  }

  button {
    background-color: #f57c00;
    border: none;
    color: white;
    padding: 18px 64px;
    cursor: pointer;
    border-radius: 8px;
    font-weight: 700;
    font-size: 18px;
  }
}
</style>
