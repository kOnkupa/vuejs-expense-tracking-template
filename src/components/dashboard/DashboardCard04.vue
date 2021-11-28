<template>
  <dashboard-card-container title="">
    <template #main>
      <div class="text-center text-base-content space-y-3">
        <div class="avatar">
          <div class="mb-8 rounded-full w-24 h-24 object-center">
            <img :src="user.avatar" :alt="user.name + 'avatar'" />
          </div>
        </div>
        <p class="text-xl font-medium">{{ user.name }}</p>
        <p class="text-3xl font-medium text-primary">{{ user.amount }}</p>
        <p class='text-sm text-gray-500'>Total income</p>
      </div>
    </template>
  </dashboard-card-container>
</template>

<script lang="ts">
import * as faker from 'faker'
import { defineComponent, ref } from 'vue'

import DashboardCardContainer from './DashboardCardContainer.vue'

export default defineComponent({
  name: 'DashboardCard04',
  components: { DashboardCardContainer },
  setup() {
    const user = ref({
      name: faker.name.findName(),
      avatar: faker.image.people(),
      amount: '$' + faker.datatype.number({ min: 100, max: 1000 }),
    })
    return {
      user,
    }
  },
})
</script>
