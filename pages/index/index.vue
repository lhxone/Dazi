<template>
	<view class="content">
		<image class="logo" src="/static/Dazi.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<uni-section title="">
			<view>
				<button @click="openCRM">点击寻找</button>
			</view>
		</uni-section>

		<uni-section title="">
			<view>
				<button @click="openCreate">点击创建</button>
			</view>
		</uni-section>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '欢迎来到Dazi ━(*｀∀´*)ノ亻!'
			}
		},
		onLoad() {

		},
		methods: {
			openCRM() {
				uni.navigateTo({
					url: "/pages/index/appCRM/appCRM"
				});
			},
			openCreate() {
				uni.navigateTo({
					url: "/pages/index/create/create"
				});
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>