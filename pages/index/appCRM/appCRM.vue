<template>
	<view>
		<uni-card v-for="(item,index) in dataList" :title="item.from+' -> '+item.to" :sub-title="item.type==0?'寻车':'寻人'"
			@click="onClick(item)">
			<text class="uni-body">这是一个带头像和双标题的基础卡片，此示例展示了一个完整的卡片。</text>
		</uni-card>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				dataList: [{
						"id": 3000,
						"from": "广州市",
						"to": "中山",
						"type": "0",
						"remark": "WoRhroL9c7"
					},
					{
						"id": 3001,
						"from": "东莞",
						"to": "成都市",
						"type": "1",
						"remark": "prWl5aohc9"
					},
					{
						"id": 3002,
						"from": "深圳",
						"to": "广州市",
						"type": "0",
						"remark": "XoMSRK6wpv"
					},
					{
						"id": 3003,
						"from": "北京市",
						"to": "东莞",
						"type": "1",
						"remark": "TimfTep7xS"
					},
					{
						"id": 3004,
						"from": "成都市",
						"to": "广州市",
						"type": "0",
						"remark": "5sTwSxD3yk"
					},
					{
						"id": 3005,
						"from": "成都市",
						"to": "成都市",
						"type": "1",
						"remark": "dmVikFIh2E"
					},
					{
						"id": 3006,
						"from": "北京市",
						"to": "成都市",
						"type": "0",
						"remark": "GYXHhbUYxP"
					},
					{
						"id": 3007,
						"from": "东莞",
						"to": "北京市",
						"type": "1",
						"remark": "CjLrgWwU5n"
					},
					{
						"id": 3008,
						"from": "东莞",
						"to": "成都市",
						"type": "0",
						"remark": "vzYYer1SBw"
					},
					{
						"id": 3009,
						"from": "广州市",
						"to": "深圳",
						"type": "0",
						"remark": "HhNRVWYB8A"
					},
					{
						"id": 3010,
						"from": "广州市",
						"to": "广州市",
						"type": "0",
						"remark": "Q9RLVWm0pz"
					},
					{
						"id": 3011,
						"from": "广州市",
						"to": "成都市",
						"type": "0",
						"remark": "0CKGku48Vs"
					},
					{
						"id": 3012,
						"from": "中山",
						"to": "广州市",
						"type": "0",
						"remark": "ObJCXiLdsY"
					},
					{
						"id": 3013,
						"from": "中山",
						"to": "中山",
						"type": "0",
						"remark": "ELBdRqyYkE"
					},
					{
						"id": 3014,
						"from": "中山",
						"to": "北京市",
						"type": "0",
						"remark": "v3pkiD1LyA"
					},
					{
						"id": 3015,
						"from": "北京市",
						"to": "北京市",
						"type": "0",
						"remark": "Gg4RtkwMrx"
					},
					{
						"id": 3016,
						"from": "中山",
						"to": "北京市",
						"type": "0",
						"remark": "tVVoYQChsT"
					},
					{
						"id": 3017,
						"from": "北京市",
						"to": "深圳",
						"type": "0",
						"remark": "OZfFYhrTFp"
					},
					{
						"id": 3018,
						"from": "深圳",
						"to": "东莞",
						"type": "0",
						"remark": "HJewUFWD2f"
					},
					{
						"id": 3019,
						"from": "成都市",
						"to": "中山",
						"type": "0",
						"remark": "rpZyaQ6jeY"
					},
					{
						"id": 3020,
						"from": "深圳",
						"to": "东莞",
						"type": "0",
						"remark": "rk91N0joxh"
					}
				]
			}
		},
		methods: {
			onClick(item) {
				uni.navigateTo({
					url: "/pages/index/detail/detail?data=" + JSON.stringify(item)
				});
			}
		}
	}
</script>

<style>

</style>