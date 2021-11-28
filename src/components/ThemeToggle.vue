<template>
  <Switch
    v-model="enabled"
    :class="[
      enabled ? 'bg-indigo-600' : 'bg-gray-200',
      'relative inline-flex flex-shrink-0 h-8 w-16 border-2 border-transparent rounded-full cursor-pointer transition-colors ease-in-out duration-200 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500',
    ]"
    data-toggle-theme="dark,light"
  >
    <span class="sr-only">Theme Toggle</span>
    <span
      :class="[
        enabled ? 'translate-x-8' : 'translate-x-0',
        'pointer-events-none relative inline-block h-7 w-7 rounded-full bg-white shadow transform ring-0 transition ease-in-out duration-200',
      ]"
    >
      <span
        :class="[
          enabled ? 'opacity-0 ease-out duration-100' : 'opacity-100 ease-in duration-200',
          'absolute inset-0 h-full w-full flex items-center justify-center transition-opacity',
        ]"
        aria-hidden="true"
      >
        <sun-icon class="h-5 w-5 text-yellow-300 fill-current" />
      </span>
      <span
        :class="[
          enabled ? 'opacity-100 ease-in duration-200' : 'opacity-0 ease-out duration-100',
          'absolute inset-0 h-full w-full flex items-center justify-center transition-opacity',
        ]"
        aria-hidden="true"
      >
        <moon-icon class="h-5 w-5 text-gray-700 fill-current" />
      </span>
    </span>
  </Switch>
</template>

<script lang="ts">
import { Switch } from '@headlessui/vue'
import { defineComponent, onMounted, ref } from 'vue'

import MoonIcon from './icons/MoonIcon.vue'
import SunIcon from './icons/SunIcon.vue'

export default defineComponent({
  name: 'ThemeToggle',
  components: { Switch, MoonIcon, SunIcon },
  setup() {
    const enabled = ref(false)
    const getCurrentTheme = () => {
      const theme = localStorage.getItem('theme')
      enabled.value = theme === 'dark'
    }
    onMounted(getCurrentTheme)
    return {
      enabled,
    }
  },
})
</script>
