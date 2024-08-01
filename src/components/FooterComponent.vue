<template>
  <footer class="footer">
    <p>
      There are many variations of passages of Lorem Ipsum available, but the majority have suffered
      alteration in some form, by injected humour, or randomised words which don't look even
      slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure
      there isn't anything embarrassing hidden in the middle of text. All the Lorem Ipsum generators
      on the Internet tend to repeat predefined chunks as necessary, making this the first true
      generator on the Internet. It uses a dictionary of over 200 Latin words, combined with a
      handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The
      generated Lorem Ipsum is therefore always free from repetition, injected humour, or
      non-characteristic words etc.
    </p>
  </footer>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'FooterComponent'
})
</script>

<style scoped lang="scss">
.footer {
  color: rgba(0, 0, 0, 0.75);
  max-width: 1295px;
  margin: 0 auto;

  p {
    padding: 32px 16px;
    font-size: 10px;
    line-height: 20px;
    text-align: center;
  }

  @media (min-width: 1024px) {
    padding: 66px 0;
  }
}
</style>
