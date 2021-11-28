<template>
  <div class="flex justify-between w-full relative items-center">
    <h1 class="text-2xl font-bold sm:text-3xl">Dashboard</h1>
    <div class="flex space-x-2 items-center">
      <theme-toggle />
      <add-item-dropdown class="hidden sm:block" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

import AddItemDropdown from '../components/partials/AddItemDropdown.vue'
import ThemeToggle from '../components/ThemeToggle.vue'

export default defineComponent({
  name: 'TheTopNavbar',
  components: { AddItemDropdown, ThemeToggle },
})
</script>
