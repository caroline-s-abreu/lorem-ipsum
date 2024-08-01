<template>
  <section class="map">
    <div class="map-content">
      <div class="map-text">
        <div class="map-title">
          <h5>Lorem is simply dummy text of the printing.</h5>
        </div>
        <p>
          Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece
          of classical Latin literature from 45 BC, making it over 2000 years old.
        </p>
        <p class="description">
          There are many variations of passages of Lorem Ipsum available, but the majority have
          suffered alteration in some form.
        </p>
        <button class="desktop">
          <img src="../assets/waze.svg" alt="waze icon" />
          <span>Ir com Waze</span>
        </button>
      </div>
      <div class="map-section">
        <img class="map-image" src="../assets/map.png" alt="Map" />
        <button class="mobile">
          <img src="../assets/waze.svg" alt="waze icon" />
          <span>Ir com Waze</span>
        </button>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'MapSection'
})
</script>

<style scoped lang="scss">
.map {
  padding: 58px 16px;
  background-color: #f8f8f8;
  display: flex;
  justify-content: center;

  .map-content {
    display: flex;
    flex-direction: column;
    gap: 20px;
    max-width: 1295px;

    .map-text {
      display: flex;
      flex-direction: column;
      gap: 20px;

      .map-title {
        border-left: 8px solid #ff7c3a;
        padding: 8px 0 8px 32px;

        h5 {
          font-weight: 700;
          font-size: 32px;
          color: #810059;
          text-align: start;
        }
      }

      p {
        font-size: 20px;
        line-height: 32px;
        color: #292929;
      }
      .desktop {
        display: none;
      }
    }

    .map-section {
      display: flex;
      flex-direction: column;
      gap: 30px;
      align-items: center;

      .map-image {
        width: 100%;
        height: auto;
        border: 8px solid #fff;
      }

      button {
        padding: 13px 40px;
        border-radius: 4px;
        background-color: #05c8f7;
        font-weight: 600;
        font-size: 18px;
        line-height: 27px;
        border: none;
        display: flex;
        gap: 8px;
        align-items: center;
        cursor: pointer;
      }
    }
  }

  @media (min-width: 1024px) {
    .map-content {
      flex-direction: row;
      justify-content: space-between;

      .map-text {
        width: 50%;
        align-items: flex-start;
        gap: 24px;

        .map-title {
          padding-bottom: 16px;
        }

        .description {
          font-weight: 700;
        }

        .desktop {
          display: inline;
          padding: 13px 40px;
          border-radius: 4px;
          background-color: #05c8f7;
          font-weight: 600;
          font-size: 18px;
          line-height: 27px;
          border: none;
          display: flex;
          gap: 8px;
          align-items: center;
          cursor: pointer;
        }
      }

      .map-section {
        padding: 60px 0;

        button {
          display: none;
        }
      }
    }
  }
}
</style>
