<template>
  <div class="flex justify-between h-[60px] bg text-white">
    <span class="material-icons text-h4 w-6">menu</span>
    <img :src="imgMusic" alt="ngmusic">
    <span class="material-icons text-h4 w-6" @click="($emit('clickHeader', 'search'))">search</span>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'HeaderResult',
  data() {
    return {
      imgMusic: require('@/assets/images/ngmusic.png')
    }
  }
})
</script>

<style scoped>
.bg {
  margin: 0 0 35px;
  padding: 18px 15px 22.2px;
  box-shadow: 0 0 6px 0 #a45deb;
  background-image: linear-gradient(100deg, #712bda, #a45deb 100%);
}
</style>