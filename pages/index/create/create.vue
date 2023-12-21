<template>
	<view>
		<view>
			<form @submit="formSubmit" @reset="formReset">
				<uni-section title="出发地" type="line">
					<uni-card :is-shadow="false">
						<view class="uni-list-cell-db">
							<picker @change="bindFromPickerChange" :value="from" :range="array">
								<view class="uni-input">{{array[from]}}</view>
							</picker>
						</view>
					</uni-card>

				</uni-section>
				<uni-section title="目的地" type="line">
					<uni-card :is-shadow="false">
						<view class="uni-list-cell-db">
							<picker @change="bindToPickerChange" :value="to" :range="array">
								<view class="uni-input">{{array[to]}}</view>
							</picker>
						</view>
					</uni-card>
				</uni-section>
				<uni-section title="联系方式" type="line">
					<view class="uni-input-wrapper">
						<input class="uni-input" placeholder="在此输入联系方式" />
					</view>
				</uni-section>
				<uni-section title="备注" type="line">
					<view class="uni-input-wrapper">
						<input class="uni-input" placeholder="在此输入备注" />
					</view>
				</uni-section>
				<view class="uni-btn-v">
					<uni-section title="">
						<button form-type="submit">提交</button>
					</uni-section>
					<uni-section title="">
						<button type="default" form-type="reset">取消</button>
					</uni-section>
					<uni-section title="">
						<button class="button" @click="getLoc" type="primary">精确定位</button>
					</uni-section>
				</view>
			</form>
		</view>
	</view>
</template>


<script>
	export default {
		data() {
			return {
				title: 'picker',
				array: ['汉峪金谷', '济南站', '奥体中心', '唐冶', '张马屯', '大明湖'],
				from: 0,
				to: 0,
			}
		},
		methods: {
			formSubmit: function(e) {
				console.log('form发生了submit事件，携带数据为：' + JSON.stringify(e))
				uni.showModal({
					content: '骗你的，后台还没开发完',
					showCancel: false
				});
			},
			formReset: function(e) {
				uni.navigateBack()
			},
			getLocByMap() {
				uni.chooseLocation({
					success: function(res) {
						console.log('位置名称：' + res.name);
						console.log('详细地址：' + res.address);
						console.log('纬度：' + res.latitude);
						console.log('经度：' + res.longitude);
					}
				});
			},
			getLoc() {
				uni.showLoading({
					title: "定位中"
				})
				uni.getLocation({
					type: 'wgs84',
					success: function(res) {
						uni.hideLoading()
						console.log(res)
						uni.showModal({
							// content: '表单数据内容：' + JSON.stringify(e),
							content: "定位数据" + JSON.stringify(res),
							success: function(res) {
								if (res.confirm) {
									console.log('用户点击确定');
								} else if (res.cancel) {
									console.log('用户点击取消');
								}
							}
						});

						console.log(res)
						console.log('当前位置的经度：' + res.longitude);
						console.log('当前位置的纬度：' + res.latitude);
					}
				});


			},
			bindFromPickerChange: function(e) {
				console.log('from picker===>', e.detail.value)
				this.from = e.detail.value
			},
			bindToPickerChange: function(e) {
				console.log('to picker===>', e.detail.value)
				this.to = e.detail.value
			}
		}
	}
</script>

<style lang="scss">
	.warp {
		padding: 10px;
	}

	.button {
		margin-bottom: 10px;
	}
</style>