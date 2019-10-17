<template lang="html">

  <section>
    <energy-date-select></energy-date-select>
    <energy-display :energyStats='energyStats'></energy-display>
  </section>


</template>

<script>
import energyDisplay from "@/components/energyDisplay"
import energyDateSelect from '@/components/energyDateSelect'

export default {
  name: 'energy-controls',
  components: {
    'energy-display': energyDisplay,
    'energy-date-select': energyDateSelect
  },
  props: ['energyStats'],
}
</script>

<style lang="css" scoped>
</style>
