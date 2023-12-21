<template>
	<view>
		
	</view>
</template>

<script>
	export default {
		onLoad(option) {
			this.dataList = JSON.parse(option.data)
			console.log(this.dataList)
		},
		data() {
			return {
				dataList: {}
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
