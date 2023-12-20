<template>
	<view>
		<uni-section v-for="(item,index) in dataList">
			<uni-card :title="item.from+' -> '+item.to" :sub-title="item.type?'寻车':'寻人'" @click="onClick(item)">
				<text class="uni-body">这是一个带头像和双标题的基础卡片，此示例展示了一个完整的卡片。</text>
			</uni-card>
		</uni-section>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				dataList: [{
					"from": "历下",
					"to": "历城",
					"type": "0",
					"remark": "1"
				}, {
					"from": "历下",
					"to": "历城",
					"type": "1",
					"remark": "2"
				}, {
					"from": "历下",
					"to": "历城",
					"type": "2",
					"remark": "3"
				}, {
					"from": "历下",
					"to": "历城",
					"type": "0",
					"remark": "4"
				}, {
					"from": "历下",
					"to": "历城",
					"type": "1",
					"remark": "5"
				}]
			}
		},
		methods: {
			onClick(item) {
				console.log(item)
			}
		}
	}
</script>

<style>

</style>