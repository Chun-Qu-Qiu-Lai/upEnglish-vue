<template>
	<view style="height: 90vh;margin:5vh auto;width: 90vw;">
		<view style="height: 90rpx;line-height: 90rpx;border-radius: 10rpx;padding-left: 20rpx;padding-right: 20rpx;"
			v-for="item in list" :key="item.id" :class="item.id%2?'title-style-left':'title-style-right'"
			@click="toAnalysisContent(item.id)">
			<view style="display: flex;justify-content: space-between;">
				<view v-if="item.id%2?false:true"
					style="display: flex;height: 90rpx;align-items: center;justify-content: center;">
					<image src="https://www.shanzs.top/lhbfile/tubiaos/gongnue.png" style="width: 65rpx;height: 65rpx;"></image>
				</view>
				<view style="width: 80%; letter-spacing: 0.1rem;">
					{{item.listTitle}}
				</view>
				<view v-if="item.id%2?true:false"
					style="display: flex;height: 90rpx;align-items: center;justify-content: center;">
					<image src="https://www.shanzs.top/lhbfile/tubiaos/gongnue.png" style="width: 65rpx;height: 65rpx;"></image>
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
					listTitle: '考研英语长难句分析一'
				}, {
					id: 2,
					listTitle: '考研英语长难句分析二'
				}, {
					id: 3,
					listTitle: '考研英语长难句分析三'
				}, {
					id: 4,
					listTitle: '考研英语长难句分析四'
				}, {
					id: 5,
					listTitle: '考研英语长难句分析五'
				}, {
					id: 6,
					listTitle: '考研英语长难句分析六'
				}, {
					id: 7,
					listTitle: '考研英语长难句分析七'
				}, {
					id: 8,
					listTitle: '考研英语长难句分析八'
				}]
			}
		},
		methods: {
			toAnalysisContent(id) {
				switch (id) {
					case 1:
						uni.navigateTo({
							url: "/pages/analysisChildNode/analysisOne"
						})
						break
					case 2:
						uni.navigateTo({
							url: "/pages/analysisChildNode/analysisTwo"
						})
						break
					case 3:
						uni.navigateTo({
							url: "/pages/analysisChildNode/analysisThree"
						})
						break
					case 4:
						uni.navigateTo({
							url: "/pages/analysisChildNode/analysisFour"
						})
						break
					case 5:
						uni.navigateTo({
							url: "/pages/analysisChildNode/analysisFive"
						})
						break
					case 6:
						uni.navigateTo({
							url: "/pages/analysisChildNode/analysisSix"
						})
						break
					case 7:
						uni.navigateTo({
							url: "/pages/analysisChildNode/analysisSeven"
						})
						break
					case 8:
						uni.navigateTo({
							url: "/pages/analysisChildNode/analysisEight"
						})
						break
				}
			}
		},

	}
</script>

<style>
	page {
		background-color: #f5f5f5;
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
