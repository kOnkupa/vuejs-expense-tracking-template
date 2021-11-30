<template>
  <dashboard-card-container title="Transactions">
    <template #main>
      <div class="overflow-x-auto overflow-y-auto max-h-96">
        <table class="table w-full">
          <thead>
            <tr>
              <th>Date</th>
              <th>Name</th>
              <th>Amount</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in randomDataTable" :key="item.id">
              <td>{{ item.date }}</td>
              <td>{{ item.name }}</td>
              <td>${{ item.amount }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </template>
  </dashboard-card-container>
</template>

<script lang="ts">
import dayjs from 'dayjs'
import * as faker from 'faker'
import { computed, defineComponent } from 'vue'

import DashboardCardContainer from './DashboardCardContainer.vue'

export default defineComponent({
  name: 'DashboardCard02',
  components: { DashboardCardContainer },
  setup() {
    const randomDataTable = computed(() =>
      Array.from(Array(10).keys()).map(() => ({
        id: faker.datatype.uuid(),
        name: faker.company.companyName(),
        date: dayjs(faker.datatype.datetime()).format('DD/MM/YYYY'),
        amount: faker.finance.amount(),
      }))
    )
    return {
      randomDataTable,
    }
  },
})
</script>
