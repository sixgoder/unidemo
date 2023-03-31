<template>
	<view>
		<form @submit="onSubmit">
			<view class="row">
				<input type="text" name="username">
			</view>
			<view class="row">
				<textarea name="content"></textarea>
			</view>
			<view class="row">
				<radio-group name="gender">
					<radio value="0">女</radio>
					<radio value="1">男</radio>
					<radio value="2" checked>保密</radio>
				</radio-group>
			</view>
			<view class="row">
				<picker :range="options" @change="onPickerChange" name="graduated" :value="selecteValue">
					<view>点击选择学历：{{options[selecteValue]}}</view>
				</picker>

			</view>
			<view class="row">
				<button form-type="submit" type="primary">提交信息</button>
				<button form-type="reset">重置信息</button>
			</view>
		</form>
		{{obj}}
		<view class="row">
			<input type="text" v-model="title">
			<view>原标题：{{title}}</view>
			<view>修改后：{{changeTitle}}</view>
		</view>
		<myitem></myitem>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				obj: null,
				options: ['高中', '大专', '本科', '硕士', '博士'],
				selecteValue: 2,
				title: ""
			};
		},
		methods: {
			onSubmit(e) {
				console.log(e)
				this.obj = e.detail.value
			},
			onPickerChange(e) {
				console.log(e)
				this.selecteValue = e.detail.value
			}
		},
		// 这里的方法按属性使用
		// 计算属性基于响应式依赖进行缓存相比methods来说
		computed: {
			changeTitle() {
				return this.title.toLocaleUpperCase()
			}
		}
	}
</script>

<style lang="scss">
	.row {
		margin: 20rpx 20px;

		input,
		textarea {
			border: 1rpx solid dodgerblue;
			width: 100%;
		}

		button {
			margin-top: 20rpx;
		}

		radio {
			margin-right: 20rpx;
		}
	}
</style>