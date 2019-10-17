<template lang="html">

  <div class="">
    <h4>See Energy Usage</h4>
    <label for="From">From: </label>
    <input v-model='selectedDates.from' type="date" name="From" value="">
    <label for="To">To:</label>
    <input v-model='selectedDates.to' type="date" name="To" value="">
  </div>

</template>

<script>


export default {
  name: 'date-select',
  data() {
    return {
      selectedDates: {
        from: null,
        to: null
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>
