<template>
	<div v-if="show" class="relative loading-page">
    <div class="absolute right-4 top-4">
      <span class="material-icons text-h4 w-6 text-white" @click="($emit('clickModal', 'close'))">close</span>
    </div>
    <div class="flex mt-60 items-center ">
      <div class="w-full lg:w-1/4 px-[15px]">
        <p class="font-bold text-white text-[20px] text-center mb-[30px]">Search</p>
        <input-text v-model="search" class="mb-[15px]" />
        <button-rounded text="Search" bg-button="#712bda" @clickButton="handleClick" />
      </div>
    </div>
	</div>
</template>

<script>
export default{
	components: {
    ButtonRounded: () => import('@/components/support/ButtonRounded.vue'),
    InputText: () => import('@/components/support/InputText.vue')
  },
  props: {
		show: { type: Boolean, default: false }
	},
  data() {
    return {
      search: ''
    }
  },
  watch: {
    show() {
      this.search = this.$route?.query?.search || null
    }
  },
  methods: {
    handleClick() {
      const search = this.search ? `?search=${this.search}` : ''
      this.$router.push(`/result${search}`)
      this.$emit('clickModal', 'close')
    }
  }
}
</script>

<style scoped>
.loading-page {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background: rgba(28 28 45 / 90%);
	z-index: 100;
}
</style>