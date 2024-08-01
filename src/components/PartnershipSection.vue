<template>
  <section class="partnership-container">
    <div class="partnership-content">
      <p class="partnership-title">
        Lorem Ipsum is simply dummy text of the printing and typesetting industry
      </p>
      <p class="partnership-description">
        Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an
        unknown printer took a galley of type and scrambled it to make a type specimen book. It has
        survived not only five centuries, but also the leap into electronic typesetting, remaining
        essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets
        containing Lorem Ipsum passages, and more recently with desktop publishing software like
        Aldus PageMaker including versions of Lorem Ipsum.
      </p>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PartnershipSection'
})
</script>

<style scoped lang="scss">
.partnership-container {
  background-image: url('../assets/background.png');
  background-color: #424242;

  .partnership-content {
    max-width: 982px;
    padding: 134px 16px;
    color: #fafafa;
    text-align: center;

    .partnership-title {
      font-weight: 700;
      font-size: 32px;
      line-height: 39px;
    }

    .partnership-description {
      display: none;
      padding: 0 54px;
    }
  }

  @media (min-width: 1024px) {
    .partnership-content {
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 32px;

      .partnership-description {
        display: inline;
        font-size: 14px;
        line-height: 24px;
      }
    }
  }
}
</style>
