<template>
  <div>
    <div :style="buttonContainerStyle">
      <button :class="buttonClass('medium')" @mouseover="showTooltip[1] = true" @mouseleave="showTooltip[1] = false">
        <span class="fa fa-star"></span>
        Button 1
        <div v-if="showTooltip[1]" class="tooltip" :style="tooltipPosition">
          Tooltip for Button 1
        </div>
      </button>

      <button :class="buttonClass('medium')" @mouseover="showTooltip[2] = true" @mouseleave="showTooltip[2] = false">
        <span class="fa fa-heart"></span>
        Button 2
        <div v-if="showTooltip[2]" class="tooltip" :style="tooltipPosition">
          Tooltip for Button 2
        </div>
      </button>

      <button :class="buttonClass('medium')" @mouseover="showTooltip[3] = true" @mouseleave="showTooltip[3] = false">
        <span class="fa fa-check"></span>
        Button 3
        <div v-if="showTooltip[3]" class="tooltip" :style="tooltipPosition">
          Tooltip for Button 3
        </div>
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      showTooltip: { 1: false, 2: false, 3: false },
    };
  },
  computed: {
    tooltipPosition() {
      return { top: '-20px', right: '50%' };
    },
    buttonContainerStyle() {
      return {
        display: 'flex',
        gap: '10px',
      };
    },
  },
  methods: {
    buttonClass(size: string) {
      return `button-${size}`;
    },
  },
});
</script>

<style scoped>
.button-small {
  font-size: 12px;
}

.button-medium {
  font-size: 16px;
}

.button-large {
  font-size: 20px;
}

.tooltip {
  position: absolute;
  background-color: #333;
  top:10px;
  color: #fff;
  padding: 5px;
  border-radius: 5px;
  z-index: 1;
}
</style>
