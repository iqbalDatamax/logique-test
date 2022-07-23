<template>
  <div class="bg h-screen px-[30px] py-[25-px]">
    <div class="h-4/5 flex items-center justify-center">
      <img :src="imgLogo" alt="logo">
    </div>
    <div>
      <input-text v-model="search" class="mb-[15px]" />
      <button-rounded text="Search" @clickButton="handleClick" />
    </div>
  </div>
</template>


<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'PageHome',
  components: {
    ButtonRounded: () => import('@/components/support/ButtonRounded.vue'),
    InputText: () => import('@/components/support/InputText.vue')
  },
  data() {
    return {
      imgLogo: require('@/assets/images/logo.png'),
      search: ''
    }
  },
  methods: {
    handleClick() {
      const search = this.search ? `?search=${this.search}` : ''
      this.$router.push(`/result${search}`)
    }
  }
})
</script>
<style scoped>
.bg {
  background-image: linear-gradient(153deg, #712bda, #a45deb 100%);
}
</style>