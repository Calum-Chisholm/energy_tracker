<template lang="html">
  <h1></h1>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      energyStats: []
    }
  },
  mounted(){
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(res => res.json())
    .then(data => this.energyStats = data);
  }
}
</script>

<style lang="css" scoped>
</style>
