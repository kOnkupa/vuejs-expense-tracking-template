<template>
  <div>
    <apexchart width="100%" height="300" :options="options" :series="series"></apexchart>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'LineChart01',
  props: {
    options: {
      type: Object,
      required: true,
    },
    series: {
      type: Array,
      required: true,
    },
  },
})
</script>
