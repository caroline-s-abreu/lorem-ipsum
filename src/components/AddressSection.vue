<template>
  <section class="address-container">
    <div class="address-content">
      <div class="address-item" v-for="address in addresses" :key="address.id">
        <div class="localization">
          <img src="../assets/pin.svg" alt="pin icon" />
          <span>Lorem Ipsum</span>
        </div>
        <span class="distance">{{ address.distance }}</span>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'AddressSection',
  data() {
    return {
      addresses: [
        { id: 1, distance: '18,6' },
        { id: 2, distance: '32,6' },
        { id: 3, distance: '45' },
        { id: 4, distance: '56,2' }
      ]
    }
  }
})
</script>

<style scoped lang="scss">
.address-container {
  padding: 32px;

  .address-content {
    margin: 0 auto;
    max-width: 1295px;
    display: flex;
    flex-direction: column;
    gap: 32px;
    align-items: center;

    .address-item {
      display: flex;
      gap: 8px;
      align-items: center;

      .localization {
        display: flex;
        align-items: center;
        gap: 2px;

        span {
          font-weight: 700;
          font-size: 18px;
          color: #810059;
          line-height: 22px;
        }
      }

      .distance {
        font-size: 18px;
        line-height: 22px;
        color: #292929;
      }
    }
  }
}

@media (min-width: 1024px) {
  .address-container {
    background-color: #f8f8f8;
    padding: 48px 0 64px 0;

    .address-content {
      flex-direction: row;
      justify-content: space-between;
    }
  }
}
</style>
