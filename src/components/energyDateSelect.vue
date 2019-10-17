<template lang="html">

  <div class="">
    <h4>See Energy Usage</h4>
    <label for="From">From: </label>
    <input v-on:change='handleDateChange' v-model='selectedDates.from' type="date" name="From" value="">
    <label for="To">To:</label>
    <input v-on:change='handleDateChange' v-model='selectedDates.to' type="date" name="To" value="">
  </div>

</template>

<script>
import {eventBus} from '@/main.js';

export default {
  name: 'date-select',
  data() {
    return {
      selectedDates: {
        from: null,
        to: null
      }
    }
  },
  methods: {
    handleDateChange() {
      if (this.selectedDates.from && this.selectedDates.to) {
      eventBus.$emit('selected-dates', this.selectedDates)
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>
