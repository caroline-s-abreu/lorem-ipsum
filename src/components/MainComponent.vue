<template>
  <section class="container">
    <FeaturesComponent />
    <FormSection />
    <ContentSection />
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import FeaturesComponent from './FeaturesComponent.vue'
import FormSection from './FormSection.vue'
import ContentSection from './ContentSection.vue'

export default defineComponent({
  name: 'MainComponent',
  components: {
    FeaturesComponent,
    FormSection,
    ContentSection
  }
})
</script>

<style scoped lang="scss">
.container {
  background: linear-gradient(90deg, #59337e 0%, #bf3f59 100%);
  border-top: 8px solid #bf3f59;
  padding: 16px;
}
</style>
