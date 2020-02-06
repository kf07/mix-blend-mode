<template>
  <div>
    <label>1つ目の色
      <input type="text" v-model="colors.color1" />
    </label>
    <label>2つ目の色
      <input type="text" v-model="colors.color2" />
    </label>
    <label>3つ目の色
      <input type="text" v-model="colors.color3" />
    </label>
  </div>
</template>

<script>
  import { ref } from '@vue/composition-api';
  export default {
    name: "ColorSelect",
    props: {
      color: {
        type: Object,
        default: ''
      }
    },
    setup(props,context) {
    const colors = ref(props.color)
     return {
       colors
     }
    }
  }
</script>

<style scoped>

</style>
