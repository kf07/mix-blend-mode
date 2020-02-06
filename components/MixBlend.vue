<template>
  <div>
    <div class="blend">
      <div class="circle first-color" :style="{ backgroundColor: colorList.color1 }"></div>
      <div class="circle second-color" :style="{ backgroundColor: colorList.color2 }"></div>
      <div class="circle third-color" :style="{ backgroundColor: colorList.color3 }"></div>
    </div>
    <ColorSelect :color=colorList />
  </div>
</template>

<script>
  import { ref } from '@vue/composition-api'
  import ColorSelect from "./ColorSelect";
  export default {
    name: "MixBlend",
    components: {ColorSelect},
    setup() {
      const colorList = ref({
        color1: '#f00',
        color2: '#00f',
        color3: '#0f0'
      })
      const handleClick = (color) => {
        colorList.value = color
      }
      return {
        colorList,
        handleClick
      }
    }
  }
</script>

<style scoped>
.blend {
  position: relative;
  width: 260px;
  height: 260px;
  margin: auto;
}
.first-color {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: #f00;
}
.second-color {
  right: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: #00f;
}

.third-color {
  right: 0;
  left: 0;
  margin: auto;
  bottom: 0;
  width: 100%;
  height: 100%;
  background-color: #0f0;
}

.circle {
  mix-blend-mode: screen;
  position: absolute;
  width: 160px;
  height: 160px;
  border-radius: 50%;
}
</style>
