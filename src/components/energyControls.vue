<template lang="html">
  <energy-display :energyStats='energyStats'></energy-display>
</template>

<script>
import energyDisplay from "@/components/energyDisplay"

export default {
  name: 'energy-controls',
  components: {
    'energy-display': energyDisplay,
  },
  props: ['energyStats']
}
</script>

<style lang="css" scoped>
</style>
