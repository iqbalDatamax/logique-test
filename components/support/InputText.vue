<template>
  <div>
    <input v-model="valueContent" :type="type" class="base-input" placeholder="Artist / Album / Title" autocomplete="false">
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'InputText',
  props: {
    type: { type: String, default: 'text', validator: (item) => ['text', 'number', 'search', 'password', 'date', 'email', 'tel', ].includes(item) },
    value: { type: [Number, String], default: null }
  },
  computed: {
    valueContent: {
			get(): any {
				return (this as any).value
			},
			set(value): void {
				;(this as any).$emit('input', value)
			}
		},
  }
})
</script>