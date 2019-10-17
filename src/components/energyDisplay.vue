<template lang="html">
  <!-- <GChart></GChart> -->
  <GChart
  type="ColumnChart"
  :data='formattedData'
  :options='chartOptions'
  />

</template>

<script>
import { GChart } from 'vue-google-charts'

export default {
  name: 'energy-display',
  data(){
    return {
      chartOptions: {
        chart: {
          title: 'Energy Usage Percentages',
          subtitle: 'Energy Usage by Percentage',
        }
      }
    }
  },
  computed: {
    formattedData: function() {
      if (!this.energyStats) return;

      const formattedData = this.energyStats.data.generationmix.map((fuelObject) => {
        return [fuelObject.fuel, fuelObject.perc]
      })
      formattedData.unshift(['Fuel', 'Percentage'])
      return formattedData
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
