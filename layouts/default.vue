<template>
  <div>
    <div class="flex flex-col bg-secondary">
      <div class="min-h-screen z-20 lg:w-[420px] lg:mx-auto bg-white">
        <Nuxt />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'LayoutDefault'
})
</script>