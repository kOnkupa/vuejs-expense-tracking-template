<template>
  <div class="flex items-center cursor-pointer py-2 px-4 rounded-box hover:bg-primary-focus">
    <slot name="icon" />
    <p class="ml-2">{{ label }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'TheSidebarLink',
  props: {
    label: {
      type: String,
      required: true,
    }
  },
})
</script>
