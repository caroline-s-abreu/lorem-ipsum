<template>
  <header class="header">
    <div class="container-header">
      <img class="logo" src="@/assets/logo.png" alt="Logo" />
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HeaderComponent'
})
</script>

<style scoped lang="scss">
.header {
  background: linear-gradient(90deg, #cf4245 0%, #810059 100%);
  text-align: center;
  height: 100px;

  .container-header {
    position: relative;
    max-width: 1295px;
    display: flex;
    margin: 0 auto;

    .logo {
      position: absolute;
      top: 40px;
      width: 156px;
    }
  }

  @media (max-width: 768px) {
    padding: 1rem;
  }
}
</style>
