<template>
  <section class="content-container">
    <div class="content-section" v-for="content in contents" :key="content.id">
      <div class="text-group">
        <div class="title-container">
          <h4>{{ content.title }}</h4>
        </div>
        <p class="content1">{{ content.content1 }}</p>
        <div class="content-text-footer">
          <p class="content2">{{ content.content2 }}</p>
          <p class="content3">{{ content.content3 }}</p>
        </div>
      </div>
      <img :src="content.image" alt="Content Image" />
    </div>
    <div class="carousel-container">
      <carousel :items-to-show="2.5">
        <slide v-for="item in apiData" :key="item.id">
          <div class="carousel__item">
            <div class="status-container">
              <div :class="['status-label', getStatusClass(item.status)]">
                <span class="status-icon" :class="getStatusIcon(item.status)"></span>
                {{ getStatusText(item.status) }}
              </div>
            </div>
            <img :src="Image3" alt="Content Image" class="carousel__image" />
            <div class="carousel__details">
              <div class="price-container">
                <p class="price">a partir de {{ formatPrice(item.Valor) }}</p>
              </div>
              <p class="name">{{ item.Nome }}</p>
            </div>
          </div>
        </slide>
      </carousel>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Image1 from '@/assets/image1.png'
import Image3 from '@/assets/image3.jpg'
import axios from 'axios'
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide } from 'vue3-carousel'

interface Imovel {
  id: string
  status: number
  Valor: string
  Nome: string
}

export default defineComponent({
  name: 'ContentSection',
  components: {
    Carousel,
    Slide
  },
  data() {
    return {
      contents: [
        {
          id: 1,
          title: 'Título Opt 1',
          content1: 'Contrary to popular belief, Lorem Ipsum is not simply random text.',
          content2:
            'The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. ',
          content3:
            'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.',
          image: Image1
        }
      ],
      apiData: [] as Imovel[],
      Image3
    }
  },
  mounted() {
    axios
      .get('https://298dc7b0d9ef4714a086a3c09c305965.api.mockbin.io/')
      .then((response) => {
        console.log(response.data.imoveis.imovel)
        this.apiData = response.data.imoveis.imovel
      })
      .catch((error) => {
        console.error('Erro ao buscar dados da API:', error)
      })
  },
  methods: {
    getStatusText(status: number) {
      switch (status) {
        case 1:
          return 'Em construção'
        case 2:
          return 'Pronto para morar'
        case 3:
          return '100% Vendido'
        default:
          return ''
      }
    },
    getStatusClass(status: number) {
      switch (status) {
        case 1:
          return 'in-construction'
        case 2:
          return 'ready-to-move'
        case 3:
          return 'sold-out'
        default:
          return ''
      }
    },
    getStatusIcon(status: number) {
      switch (status) {
        case 1:
          return 'icon-construction'
        case 2:
          return 'icon-ready'
        case 3:
          return 'icon-sold'
        default:
          return ''
      }
    },
    formatPrice(value: string) {
      const numberValue = parseFloat(value)
      return new Intl.NumberFormat('pt-BR', { style: 'currency', currency: 'BRL' }).format(
        numberValue
      )
    }
  }
})
</script>

<style scoped lang="scss">
.content-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  margin-top: 40px;

  .content-section {
    max-width: 1295px;
    width: 100%;

    .text-group {
      display: flex;
      flex-direction: column;
      gap: 8px;
      color: #fff;
      text-align: start;

      .title-container {
        border-left: 8px solid #ff7c3a;
        padding: 8px 32px;

        h4 {
          font-weight: 700;
          font-size: 32px;
        }
      }

      .content1 {
        font-weight: 700;
        font-size: 20px;
        line-height: 35px;
      }

      .content-text-footer {
        display: flex;
        flex-direction: column;
        gap: 8px;

        .content2,
        .content3 {
          font-weight: 400;
          font-size: 16px;
          line-height: 30px;
        }
      }
    }

    img {
      width: 100%;
      height: auto;
    }

    &:first-of-type {
      margin-bottom: 60px;
    }
  }

  button {
    border-radius: 8px;
    background-color: #f57c00;
    color: #fff;
    padding: 18px 64px;
    font-weight: 700;
    font-size: 18px;
    border: none;
    cursor: pointer;
  }

  .carousel-container {
    width: 100%;
    max-width: 1295px;

    .carousel__item {
      position: relative;
      border: 1px solid #ddd;
      border-radius: 8px;
      overflow: hidden;
      background-color: #fff;
      text-align: center;
      margin: 0 10px;

      .status-container {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        display: flex;
        justify-content: center;
        padding: 10px;
      }

      .status-label {
        display: flex;
        align-items: center;
        padding: 5px 10px;
        border-radius: 4px;
        color: #fff;
        font-weight: bold;
        background-color: rgba(77, 77, 77, 0.342);
        z-index: 1;

        .status-icon {
          margin-right: 5px;

          &.icon-construction::before {
            content: '🔧';
          }

          &.icon-ready::before {
            content: '🏠';
          }

          &.icon-sold::before {
            content: '❌';
          }
        }
      }

      img.carousel__image {
        width: 100%;
        height: auto;
      }

      .carousel__details {
        padding: 10px;

        .price-container {
          background-color: #673ab7;
          color: #fff;
          padding: 5px;
          border-radius: 4px;
          display: inline-block;
          margin-bottom: 5px;

          .price {
            font-size: 16px;
            font-weight: bold;
          }
        }

        .name {
          font-size: 14px;
          color: #666;
        }
      }
    }
  }

  @media (min-width: 1024px) {
    .content-section {
      display: flex;
      align-items: center;
      gap: 100px;

      .text-group {
        gap: 32px;
      }

      img {
        width: 500px;
        height: auto;
      }
    }
  }
}
</style>
