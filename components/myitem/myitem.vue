<template>
	<view>
		<view class="item" :style="{height:state?'300rpx':0}">
			传值：{{title}}
		</view>
		<view class="time">
			时间戳：{{time}}
		</view>
		<view>
			<input type="text" placeholder="请输入..." @input="onInput">
		</view>
		<button size="mini" @click="onClose">关闭</button>
	</view>
</template>

<script>
	export default {
		name: "myitem",
		// props: ["title"],
		props: {
			title: {
				type: String,
				default: '默认值'
			},
			time: {
				type: Number,
				default: Date.now()
			},
			state: {
				type: Boolean,
				default: false
			}
		},
		data() {
			return {

			};
		},
		methods: {
			onInput(e) {
				this.$emit("inputEvent", e.detail.value)
			},
			onClose() {
				this.$emit("update:state", false)
			}
		}
	}
</script>

<style lang="scss">
	.item {
		width: 300rpx;
		height: 300rpx;
		background-color: #3af;
		color: yellow;
	}
</style>