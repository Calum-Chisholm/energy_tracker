<template lang="html">
  <div class="">
    <h1>Energy Percentages</h1>
    <energy-controls :energyStats='this.energyStats'></energy-controls>
  </div>
</template>

<script>
import energyControls from '@/components/energyControls'
import {eventBus} from './main.js';

export default {
  name: 'app',
  data() {
    return {
      energyStats: null,
      selectedDates: null
    }
  },
  mounted(){
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(res => res.json())
    .then(data => this.energyStats = data);

    eventBus.$on('selected-dates', (dates) => {
      this.selectedDates = dates
    })
  },
  components: {
    'energy-controls': energyControls
  }
}
</script>

<style lang="css" scoped>
</style>
