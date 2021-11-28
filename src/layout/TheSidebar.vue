<template>
  <section class="relative">
    <div class="p-2 rounded-box space-y-5 bg-primary h-full relative shadow-md text-white">
      <p class="text-xl font-bold px-4 pb-4">Expense</p>
      <the-sidebar-link v-for="(navigation, key) in navigations" :key="key" :label="navigation.title" :icon="navigation.icon" />
      <div class="flex absolute bottom-2 w-full pr-4">
        <button class="w-full flex btn btn-error rounded-box">
          <component :is="logout.icon" class="fill-current h-7 w-7" />
          <span class="ml-2">{{ logout.title }}</span>
        </button>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

import ActivityIcon from '../components/icons/ActivityIcon.vue'
import HomeIcon from '../components/icons/HomeIcon.vue'
import LogoutIcon from '../components/icons/LogoutIcon.vue'
import SettingIcon from '../components/icons/SettingIcon.vue'
import TheSidebarLink from '../layout/TheSidebarLink.vue'

const navigations = [
  {
    title: 'Dashboard',
    icon: HomeIcon,
  },
  {
    title: 'Transactions',
    icon: ActivityIcon,
  },
  {
    title: 'Settings',
    icon: SettingIcon,
  },
]
const logout = {
  title: 'Logout',
  icon: LogoutIcon,
}
export default defineComponent({
  name: 'TheSidebar',
  components: { TheSidebarLink },
  setup() {
    return {
      navigations,
      logout,
    }
  },
})
</script>
