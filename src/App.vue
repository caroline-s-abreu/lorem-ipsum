<template>
  <div id="app">
    <HeaderComponent />
    <HeroSection />
    <MainComponent />
    <MapSection />
    <AddressSection />
    <PartnershipSection />
    <FooterComponent />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import HeaderComponent from './components/HeaderComponent.vue'
import FooterComponent from './components/FooterComponent.vue'
import HeroSection from './components/HeroSection.vue'
import MainComponent from './components/MainComponent.vue'
import MapSection from './components/MapSection.vue'
import AddressSection from './components/AddressSection.vue'
import PartnershipSection from './components/PartnershipSection.vue'

export default defineComponent({
  name: 'App',
  components: {
    HeaderComponent,
    HeroSection,
    MainComponent,
    MapSection,
    AddressSection,
    PartnershipSection,
    FooterComponent
  }
})
</script>

<style lang="scss">
#app {
  font-family: 'Montserrat', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0;
}

p,
h1,
h2,
h3,
h4,
h5 {
  margin: 0;
}

button.cta-button {
  background-color: orange;
  border: none;
  padding: 0.5rem 1rem;
  color: white;
  cursor: pointer;
  font-size: 1rem;
}

@media (max-width: 768px) {
  button.cta-button {
    font-size: 0.875rem;
    padding: 0.5rem 0.75rem;
  }
}
</style>
