<template>
	<view :style="mrBoxStyle">
		<view :class="['myp-bg-'+(type&&type.length>0?type:'border')]" :style="mrDividerStyle"></view>
	</view>
</template>

<script>
	export default {
		props: {
			vertical: {
				type: Boolean,
				default: false
			},
			boxBg: {
				type: String,
				default: ''
			},
			bg: {
				type: String,
				default: ''
			},
			type: {
				type: String,
				default: ''
			},
			left: {
				type: String,
				default: '0'
			},
			right: {
				type: String,
				default: '0'
			},
			width: {
				type: String,
				default: '1px'
			},
			height: {
				type: String,
				default: '1px'
			}
		},
		computed: {
			mrBoxStyle() {
				if (this.boxBg && this.boxBg.length > 0) {
					return `background-color:${this.boxBg};`
				}
				return ""
			},
			mrDividerStyle() {
				let _style = `height:${this.height};margin-left:${this.left};margin-right:${this.right};`
				if (this.bg && this.bg.length > 0) {
					_style += `background-color:${this.bg};`
				}
				if (this.vertical) {
					_style += `width:${this.width};`
				}
				return _style
			}
		}
	}
</script>

<style lang="scss">
</style>
