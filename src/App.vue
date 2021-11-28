<template>
  <the-navbar />
  <div class="max-w-screen-2xl min-h-screen mx-auto flex py-4 px-2 sm:p-6 sm:space-x-3">
    <the-sidebar class="flex-grow w-52 hidden sm:block" />
    <div class="grid grid-cols-12 gap-3 flex-shrink w-full">
      <the-top-navbar class="col-span-12"/>
      <div class="col-span-12 space-y-3 sm:col-span-8">
        <!--   Area + Line Charts   -->
        <dashboard-card03 class="col-span-3" />
        <!--  Transaction Table  -->
        <dashboard-card02 class="col-span-3" />
      </div>
      <div class="col-span-12 space-y-3 sm:col-span-4">
        <!--   User Profile   -->
        <dashboard-card04 />
        <!--   Income/Expense Summary   -->
        <dashboard-card01 />
        <!--   Help Desk   -->
        <dashboard-card05 />
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { themeChange } from 'theme-change'
import { defineComponent, onMounted } from 'vue'

import DashboardCard01 from './components/dashboard/DashboardCard01.vue'
import DashboardCard02 from './components/dashboard/DashboardCard02.vue'
import DashboardCard03 from './components/dashboard/DashboardCard03.vue'
import DashboardCard04 from './components/dashboard/DashboardCard04.vue'
import DashboardCard05 from './components/dashboard/DashboardCard05.vue'
import TheNavbar from './layout/TheNavbar.vue'
import TheSidebar from './layout/TheSidebar.vue'
import TheTopNavbar from './layout/TheTopNavbar.vue'

export default defineComponent({
  components: {
    TheNavbar,
    TheTopNavbar,
    DashboardCard05,
    TheSidebar,
    DashboardCard04,
    DashboardCard03,
    DashboardCard02,
    DashboardCard01,
  },
  setup() {
    onMounted(themeChange)
  },
})
</script>
