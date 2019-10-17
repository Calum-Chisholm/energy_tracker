<template lang="html">
  <div class="">
    <h1>Energy Percentages</h1>
    <energy-controls :energyStats='this.energyStats'></energy-controls>
  </div>
</template>

<script>
import energyControls from '@/components/energyControls'

export default {
  name: 'app',
  data() {
    return {
      energyStats: null
    }
  },
  mounted(){
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(res => res.json())
    .then(data => this.energyStats = data);
  },
  components: {
    'energy-controls': energyControls
  }
}
</script>

<style lang="css" scoped>
</style>
