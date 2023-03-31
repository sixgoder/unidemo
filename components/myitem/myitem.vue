<template>
	<view>
		<view class="item">
			传值：{{title}}
		</view>
	</view>
</template>

<script>
	export default {
		name: "myitem",
		props: ["title"],
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