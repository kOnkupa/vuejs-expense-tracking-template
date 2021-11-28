<template>
  <div class="navbar border-b shadow sm:hidden">
    <div class="navbar-start">
      <menu-alt1-icon class="h-8 w-8" @click="open = true" />
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
import { MenuAlt1Icon } from '@heroicons/vue/solid'
import { defineComponent, ref } from 'vue'

import AddItemDropdown from '../components/partials/AddItemDropdown.vue'
import TheNavbarSlide from './TheNavbarSlide.vue'

export default defineComponent({
  name: 'TheNavbar',
  components: { TheNavbarSlide, AddItemDropdown, MenuAlt1Icon },
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
