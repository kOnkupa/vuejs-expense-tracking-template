<template>
<dashboard-card-container title="Help Desk">
  <template #main>
      <button class="btn-sm btn-primary btn">Contact</button>
    <help-desk-illustration class="mx-auto" />
  </template>
</dashboard-card-container>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

import HelpDeskIllustration from '../illustrations/HelpDeskIllustration.vue'
import DashboardCardContainer from './DashboardCardContainer.vue'

export default defineComponent({
  name: 'DashboardCard05',
  components: { HelpDeskIllustration, DashboardCardContainer }
})
</script>
