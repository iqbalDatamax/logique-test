<template>
  <div>
    <page-view />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'ResultPage',
  components: {
    PageView: () => import('~/components/SearchResult/pages/PageSearchResult.vue')
  }
})
</script>
