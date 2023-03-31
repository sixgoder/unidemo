<template>
	<view>
		<view class="item">
			myitem自定义组件
		</view>
	</view>
</template>

<script>
	export default {
		name: "myitem",
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss">
	.item {
		width: 300rpx;
		height: 300rpx;
		background-color: red;
		color: yellow;
	}
</style>