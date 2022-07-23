<template>
  <div class="bg-[#f8fafc] h-screen">
    <header-result @clickHeader="handleClick" />
    <div class="flex flex-row items-center justify-center">
      <p class="text-[#334155] text-3.5 ">Search result for :</p>
      <p class="text-[#7b34dd] text-[18px] font-semibold ml-2">{{search}}</p>
    </div>
    <div class="px-[15px] mt-6">
      <div v-for="(music, i) in listMusics" :key="i">
        <section-list v-bind="music" class="mb-5" />
      </div>
    </div>
    <modal-search :show="modalShow" @clickModal="handleClick" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  components: {
    HeaderResult: () => import('@/components/support/HeaderResult.vue'),
    SectionList: () => import('@/components/SearchResult/contens/SectionList.vue'),
    ModalSearch: () => import('@/components/support/ModalSearch.vue')
  },
  data() {
    return {
      modalShow: false,
      search: null as any,
      listMusics: [] as any
    }
  },
  watch: {
    '$route.query'() {
      this.initialize()
    }
  },
  mounted() {
    this.initialize()
  },
  methods: {
    async initialize() {
      this.search = this.$route?.query?.search || null
      const search = this.search.replace(' ', '+')
      const response = await this.$axios.$get(`https://itunes.apple.com/search?term=${search}&limit=30`)
      const data = response.results
      const lists = data.map((item: any) => {
        return {
          artistName: item?.artistName || null,
          genre: item?.kind || null,
          titel: item?.collectionName || null,
          price: item?.collectionPrice || null,
          imageCover: item?.artworkUrl60 || null 
        }
      })
      this.listMusics = lists
    },
    handleClick(menu: string) {
      if(menu === 'search') {
        this.modalShow = true
      } else if (menu === 'close') {
        this.modalShow = false
      }
    }
  }
})
</script>