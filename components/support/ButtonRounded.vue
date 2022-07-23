<template>
  <div>
    <button class="base-button h-[40px]" :style="`background-color: ${bgButton}; color: ${textColor}`" @click="$emit('clickButton')">{{text}}</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'ButtonRounded',
  props: {
    text: {type: String, default: 'button'},
    bgButton: {type: String, default: 'rgba(255, 255, 255, 0.2)'},
    textColor: {type: String, default: '#fff'}
  }
})
</script>