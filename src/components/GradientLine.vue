<!-- Eksempel på komponent, som bruger vue-multiselect med scoped styling -->
<template>
  <div class="gradient-line" :style="`width: ${width}px;`">
    <span :style="`width: ${percentage}%; background: ${color}`" class="inner-line"></span>
  </div>
</template>

<script lang="ts">
export default {
  name: 'GradientLine',
  props: {
    width: { type: [Number, String], required: true },
    percentage: { type: Number, required: true }
  },
  computed: {
    color() {
      if (this.percentage <= 49) {
        return '#26C223';
      }
      if (this.percentage <= 69) {
        return '#FFCB11';
      }
      if (this.percentage <= 89) {
        return '#FF9900';
      }
      return '#E22424';
    }
  }
};
</script>

<style lang="scss" scoped>
.gradient-line {
  position: relative;
  height: 4px;
  /* border-radius: 4px; */
  background: #dfdfdf;
  display: block;
}

.inner-line {
  position: absolute;
  left: 0;
  top: 0;
  height: 100%;
  /* border-radius: 4px; */
}
</style>
