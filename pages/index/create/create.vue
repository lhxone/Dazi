<template>
	<view>
		<view>
			<form @submit="formSubmit" @reset="formReset">
				<uni-section title="出发地" type="line">
					<uni-card :is-shadow="false">
						<view class="uni-list-cell-db">
							<picker @change="bindPickerChange" :value="index" :range="array">
								<view class="uni-input">{{array[index]}}</view>
							</picker>
						</view>
					</uni-card>
				</uni-section>
				<uni-section title="目的地" type="line">
					<uni-card :is-shadow="false">
						<view class="uni-list-cell-db">
							<picker @change="bindPickerChange" :value="index" :range="array">
								<view class="uni-input">{{array[index]}}</view>
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
				array: ['汉峪金谷', '济南站', '奥体中心', '唐冶'],
				index: 0,
				time: '12:01'
			}
		},
		methods: {
			formSubmit: function(e) {
				console.log('form发生了submit事件，携带数据为：' + JSON.stringify(e))
				uni.showModal({
					// content: '表单数据内容：' + JSON.stringify(e),
					content: '骗你的，后台还没开发完',
					showCancel: false
				});
			},
			formReset: function(e) {
				console.log('清空数据')
				uni.navigateTo({
					url: "/pages/index/index"
				})
			},
			bindPickerChange: function(e) {
				console.log('picker发送选择改变，携带值为', e.detail.value)
				this.index = e.detail.value
			}
		}
	}
</script>