<template>
  <div class="navbar border-b shadow sm:hidden">
    <div class="navbar-start">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" viewBox="0 0 20 20" fill="currentColor" @click="open = true">
        <path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h6a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd" />
      </svg>
    </div>
    <div class="navbar-center">
      <p class="text-lg font-bold font-mono">Fancy Logo</p>
    </div>
    <div class="navbar-end">
      <add-item-dropdown />
    </div>
  </div>
  <the-navbar-slide :open="open" @on-close="onClose" />
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

import AddItemDropdown from '../components/partials/AddItemDropdown.vue'
import TheNavbarSlide from './TheNavbarSlide.vue'

export default defineComponent({
  name: 'TheNavbar',
  components: { TheNavbarSlide, AddItemDropdown },
  setup() {
    const open = ref<boolean>(false)
    const onClose = () => open.value = false
    return {
      open,
      onClose,
    }
  }
})
</script>
