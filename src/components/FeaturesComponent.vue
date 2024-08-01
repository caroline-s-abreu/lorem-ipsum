<template>
  <div class="features">
    <div class="feature" v-for="feature in features" :key="feature.id">
      <img :src="feature.image" :alt="feature.imageAlt" />
      <h3>{{ feature.title }}</h3>
      <p v-if="feature.description">{{ feature.description }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Blueprint from '@/assets/blueprint.svg'
import File from '@/assets/file.svg'
import Scale from '@/assets/scale.svg'
import Ball from '@/assets/ball.svg'

export default defineComponent({
  name: 'FeaturesSection',
  data() {
    return {
      features: [
        {
          id: 1,
          title: 'Lotes a partir de 000 m',
          description: 'Residencias e comerciais',
          image: Blueprint,
          imageAlt: 'blueprint icon'
        },
        {
          id: 2,
          title: 'Lorem Ipsum e Lorem Ipsum',
          image: File,
          imageAlt: 'file icon'
        },
        {
          id: 3,
          title: 'Finibus Bonorum et Malorum',
          image: Scale,
          imageAlt: 'scale icon'
        },
        {
          id: 4,
          title: 'Finibus Bonorum et Malorum',
          image: Ball,
          imageAlt: 'ball icon'
        }
      ]
    }
  }
})
</script>

<style scoped lang="scss">
.features {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  padding: 40px 0;
  max-width: 1295px;
  margin: 0 auto;

  .feature {
    width: 180px;
    height: 235px;
    background: #fff;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-shadow: 0px 8px 32px 0px #5757571a;
    text-align: center;
    display: flex;
    flex-direction: column;
    gap: 10px;
    align-items: center;
    justify-content: center;

    h3 {
      font-weight: 700;
      color: #51367b;
      font-size: 14px;
    }

    p {
      font-weight: 400;
      color: #757575;
      font-size: 14px;
    }
  }

  @media (min-width: 1024px) {
    .feature {
      width: 280px;
      height: 180px;
    }
  }
}
</style>
