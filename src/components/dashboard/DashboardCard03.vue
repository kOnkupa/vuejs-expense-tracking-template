<template>
<dashboard-card-container title='Expense Over Time'>
  <template #main>
    <line-chart01 :options='lineChartData.options' :series='lineChartData.series' :width='300' :height='200'/>
  </template>
</dashboard-card-container>
</template>

<script lang='ts'>
import * as faker from 'faker'
import { defineComponent, ref } from 'vue'

import LineChart01 from '../charts/LineChart01.vue'
import DashboardCardContainer from './DashboardCardContainer.vue'

export default defineComponent({
  name: 'DashboardCard03',
  components: { LineChart01, DashboardCardContainer },
  setup() {
    const lineChartData = ref({
      options: {
        chart: {
          id: 'vuechart-example',
          toolbar: {
            show: false
          }
        },
        xaxis: {
          categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
          labels: {
            show: false
          },
          tooltip: {
            enabled: false
          }
        },
        stroke: {
          curve: 'smooth',
        },
        fill: {
          type:'solid',
          opacity: [0.35, 1],
        },
        legend: {
          show: false
        },
        tooltip: {
          enabled: true,
          x: {
            show: false
          },
          marker: {
            show: true,
          },
        },
      },
      series: [{
        name: 'series-1',
        type: 'area',
        color: '#667eea',
        data: Array.from({ length: 12 }, () => faker.datatype.number({ min: 0, max: 100 }))
      },{
        name: 'series-2',
        type: 'line',
        color:'#c2c2c2',
        data: Array.from({ length: 12 }, () => faker.datatype.number({ min: 0, max: 100 }))
      }]
    })
    return {
      lineChartData
    }
  }
})
</script>
