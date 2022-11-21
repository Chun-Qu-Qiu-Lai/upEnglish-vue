<template>
	<view style="height: 90vh;margin:5vh auto;width: 90vw;">
		<view style="height: 90rpx;line-height: 90rpx;border-radius: 10rpx;padding-left: 20rpx;padding-right: 20rpx;"
			v-for="item in list" :key="item.id" :class="item.id%2?'title-style-left':'title-style-right'"
			@click="toAnalysisContent(item.id)">
			<view style="display: flex;justify-content: space-between;">
				<view v-if="item.id%2?false:true"
					style="display: flex;height: 90rpx;align-items: center;justify-content: center;">
					<image src="https://www.shanzs.top/lhbfile/tubiaos/gongnue.png" style="width: 65rpx;height: 65rpx;">
					</image>
				</view>
				<view style="width: 80%; letter-spacing: 0.1rem;">
					{{item.listTitle}}
				</view>
				<view v-if="item.id%2?true:false"
					style="display: flex;height: 90rpx;align-items: center;justify-content: center;">
					<image src="https://www.shanzs.top/lhbfile/tubiaos/gongnue.png" style="width: 65rpx;height: 65rpx;">
					</image>
				</view>
			</view>


		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
					id: 1,
					listTitle: '2021年真题'
				}, {
					id: 2,
					listTitle: '2020年真题'
				}, {
					id: 3,
					listTitle: '2019年真题'
				}, {
					id: 4,
					listTitle: '2018年真题'
				}, {
					id: 5,
					listTitle: '2017年真题'
				}, {
					id: 6,
					listTitle: '2016年真题'
				}, {
					id: 7,
					listTitle: '2015年真题'
				}, {
					id: 8,
					listTitle: '2014年真题'
				}]
			}
		},
		methods: {
			toAnalysisContent(id) {
				switch (id) {
					case 1:
						uni.navigateTo({
							url: "/pages/zhentiContent/zhentiContentOne"
						})
						break
					case 2:
						uni.navigateTo({
							url: "/pages/zhentiContent/zhentiContentTwo"
						})
						break
				}
			}
		},

	}
</script>

<style>
	page {
		background-color: #f8f9fa;
	}

	.title-style-left {
		background-color: aqua;
		margin-top: 20rpx;
		/* font-size: 15px; */
		letter-spacing: 0.1rem;
		text-align: left;
		background-color: #e9e7fd;


	}

	.title-style-right {
		background-color: aqua;
		margin-top: 20rpx;
		font-size: 15px;
		letter-spacing: 0.1rem;
		text-align: right;
		background-color: #dbf6fd;
	}
</style>
