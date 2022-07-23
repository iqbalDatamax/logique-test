<template>
  <div>
    <page-view />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  components: {
    PageView: () => import('~/components/HomePage/pages/PageHome.vue')
  }
})
</script>
