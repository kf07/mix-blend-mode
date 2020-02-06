<template>
  <section class="container">
    <MixBlend />
  </section>
</template>

<script>
import MixBlend from '../components/MixBlend'
export default {
  components: { MixBlend }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
