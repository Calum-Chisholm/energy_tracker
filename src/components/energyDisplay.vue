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
        this.formattedData
      ],
      chartOptions: {
        chart: {
          title: 'Company Performance',
          subtitle: 'Sales, Expemses and Profit: 2014: 2015',
        }
      },
      formattedData: function() {
        const formattedData = this.energyStats.data.generationmix.map((fuelObject) => {
          return [fuelObject.fuel, fuelObject.perc]
        })
        return formattedData.unshift(['Fuel', 'Percentage'])
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
