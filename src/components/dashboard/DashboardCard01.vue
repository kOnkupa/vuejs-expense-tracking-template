<template>
  <dashboard-card-container title="Income / Expense">
    <template #main>
      <div v-for="item in items" :key="item.id" class="flex items-center space-x-3">
        <div class="rounded-box bg-indigo-300 p-3">
          <component :is="item.icon" class="w-7 h-7 fill-current text-white" />
        </div>
        <div>
          <div class='flex space-x-2'>
            <p class="font-bold text-lg">{{ item.amount }}</p>
            <p :class="['badge badge-sm', item.percent > 0 ? 'badge-success' : 'badge-error']">{{ item.percent }}%</p>
          </div>
          <p class="text-gray-500 text-xs text-base-content">{{ item.memo }}</p>
        </div>
      </div>
    </template>
  </dashboard-card-container>
</template>

<script lang="ts">
import faker from 'faker'
import { defineComponent } from 'vue'

import ReceiveSquareIcon from '../icons/ReceiveSquareIcon.vue'
import SendSquareIcon from '../icons/SendSquareIcon.vue'
import DashboardCardContainer from './DashboardCardContainer.vue'
// Dummy data
const items = [
  {
    id: 1,
    amount: '$' + faker.datatype.number({ min: 100, max: 1000 }),
    percent: faker.datatype.number({ min: -100, max: 100 }),
    icon: ReceiveSquareIcon,
    memo: 'Total amount income',
  },
  {
    id: 2,
    amount: '$' + faker.datatype.number({ min: 100, max: 1000 }),
    percent: faker.datatype.number({ min: 0, max: 100 }),
    icon: SendSquareIcon,
    memo: 'Total amount expense',
  },

]
export default defineComponent({
  name: 'DashboardCard01',
  components: { DashboardCardContainer },
  setup() {
    return {
      items,
    }
  },
})
</script>
