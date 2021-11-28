<template>
  <div class="rounded-box bg-base-100 shadow-md p-4 flex flex-col space-y-5 text-base-content">
    <p class="text-bold font-medium text-xl">{{ title }}</p>
    <slot name="main" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'DashboardCardContainer',
  props: {
    title: {
      type: String,
      required: true,
    },
  },
})
</script>
