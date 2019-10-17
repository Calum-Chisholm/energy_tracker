<template lang="html">
  <!-- <GChart></GChart> -->
  <GChart
    type="ColumnChart"
    :data='chartData'
    :options='chartOptions'
  />

</template>

<script>
import { GChart } from 'vue-google-charts'

export default {
  name: 'energy-display',
  data(){
    return {
      chartData: [
        ['Year', 'sales', 'expenses', 'profit'],
        ['2014', 1000, 400, 200],
        ['2015', 1170, 460, 250]
      ],
      chartOptions: {
        chart: {
          title: 'Company Performance',
          subtitle: 'Sales, Expemses and Profit: 2014: 2015',
        }
      }      
    }
  },
  components: {
    GChart
  },
  props: ['energyStats']
}

</script>

<style lang="css" scoped>
</style>
