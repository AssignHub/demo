<template>
  <v-text-field
    :label="label"
    type="time"
    prepend-inner-icon="mdi-clock-outline"
    hide-details
    outlined
    autocomplete="off"
    :value="value"
    @input="(value) => $emit('input', value)"
  ></v-text-field>
</template>

<style> 
input[type="time"]::-webkit-calendar-picker-indicator {
  display: none;
}
</style>

<script>
import { inRange, stringReplaceByIndex } from '@/utils/util.js'

export default {
  name: 'TimePicker',

  props: {
    label: {type: String, default: 'Pick time'},
    value: {type: String},
  },
}
</script>