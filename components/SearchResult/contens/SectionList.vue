<template>
  <div>
    <div class="w-full h-[130px] flex flex-row bg-white shadow-md rounded-lg p-3 gap-3">
      <img :src="imageCover" alt="img musik" class="rounded-lg h-[100px] w-[100px]">
      <div class="relative flex flex-col w-full">
        <div class="flex flex-col">
          <p class="text-[10px] font-medium text-[#334155]">{{artistName}}</p>
          <h4 class="text-[14px] text-[#334155] font-bold flex-wrap">{{titel}}</h4>
        </div>
        <div class="absolute bottom-0 left-0 w-full">
          <div class="flex justify-between items-center">
            <div class="py-0.5 px-1.5 bg-[#10b981] rounded-full text-[12px] text-white">{{genre}}</div>
            <div class="text-[#f5b014] flex flex-row items-center">
              <span class="material-icons">monetization_on</span>
              <p class="text-[14px] ml-2 font-bold">{{price}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    artistName: { type: String, default: 'JSON MARK' },
    genre: { type: String, default: 'Pop'},
    titel: { type: String, default: 'Rough Water (feat. Jason Mraz)'},
    price: { type: Number, default: 4.6},
    imageCover: { type: String, default: 'https://is3-ssl.mzstatic.com/image/thumb/Music115/v4/08/11/d2/0811d2b3-b4d5-dc22-1107-3625511844b5/00602537869770.rgb.jpg/30x30bb.jpg'}
  }
})
</script>