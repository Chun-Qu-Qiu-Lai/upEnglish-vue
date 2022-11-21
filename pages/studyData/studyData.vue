<template>
	<view>
		<view style="width: 80vw;margin-left: 20rpx;padding:20rpx 10rpx 10rpx 0rpx;" v-for="item in list"
			:key="item.id">
			<view style="">
				<image src="https://www.shanzs.top/lhbfile/tubiaos/studyData.png" style="width: 50rpx;height: 70rpx;">
				</image>
			</view>
			<view
				style="box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.1);width: 98%;height: 10vh;background-color: #dcdcdc;margin-left: 20rpx;border-left: 4rpx #000 solid;padding-top: 20rpx;border-bottom-right-radius: 20rpx;border-top-right-radius: 20rpx">
				<!-- 时间 -->
				<view
					style="display: flex;border: 1rpx #1cbcb4 solid;width: 70%;justify-content: space-between;border-radius: 10rpx;margin-left: 30rpx;">
					<view style="background-color: #1cbcb4;color: #fff;height: 100%;padding: 10rpx 10rpx;">
						{{item.timeYY}}
					</view>
					<view style="height: 100%;padding: 10rpx 10rpx;text-align: center;display: flex;align-items: center;margin: 0 auto;">{{item.timeHH}}</view>
				</view>
				<view style="margin-left: 30rpx;margin-top: 20rpx;font-size: 18px;letter-spacing: 0.1rem;">
					{{item.content}}
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
					content: '词汇训练',
					timeYY: ' 2022-10-24',
					timeHH: '11:23:22'
				}, {
					id: 2,
					content: ' 真题训练',
					timeYY: ' 2022-10-25',
					timeHH: '12:15:52'
				}, {
					id: 3,
					content: ' 难句分析',
					timeYY: ' 2022-10-27',
					timeHH: '17:05:32'
				}, {
					id: 4,
					content: '考试大纲 ',
					timeYY: ' 2022-11-1',
					timeHH: '15:05:02'
				}, {
					id: 5,
					content: '真题训练',
					timeYY: ' 2022-11-5',
					timeHH: '17:51:54'
				}, {
					id: 6,
					content: '作文 ',
					timeYY: ' 2022-11-5',
					timeHH: '21:34:14'
				}, {
					id: 7,
					content: '答题技巧',
					timeYY: ' 2022-11-7',
					timeHH: '14:05:44'
				}, {
					id: 8,
					content: '词汇训练',
					timeYY: ' 2022-11-9',
					timeHH: '08:55:29'
				}, ]
			}
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #f5f5f5;
	}
</style>
