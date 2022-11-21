<template>
	<view class="max" style="padding-top: 55rpx;">
		<view style="width: 90%;margin: auto;margin-bottom: 60rpx;" v-for="item in messages" :key="item.id">
			<view style="background-color: #f2e18c;">
				<view style="display: flex;border: 4prx red solid;line-height: 70rpx;width: 50%;padding: 20rpx;">
					<view
						style="color: black;background-color: #fff;padding-left: 10rpx;padding-right: 10rpx;color: #a5da67;border-top-left-radius: 10rpx;border-bottom-left-radius: 10rpx;">
						{{item.edition}}
					</view>
					<view
						style="background-color: #dfdfdf;padding-left: 10rpx;padding-right: 10rpx;color: #a3a3a3;border-top-right-radius: 10rpx;border-bottom-right-radius: 10rpx;">
						{{item.time}}
					</view>
				</view>

			</view>
			<view style="background-color: #f7edba;border-radius: 20rpx;padding-left: 20rpx;padding-bottom: 20rpx;">
				<view style="margin-top:40rpx;font-size: 16px;color: #4c4c4c;" v-for="(items,index) in item.content"
					:key="index">{{items}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	import requestUrl from "../../api/request.js"
	export default {
		data() {
			return {
				messages: [{
						id: 1,
						edition: 'v1.0.0',
						time: '2020/05/07',
						content: [
							'初次见面，多多关照！'
						]
					}, {
						id: 2,
						edition: 'v1.0.3',
						time: '2020/05/10',
						content: [
							'1、新增核心词汇模块',
							'2、新增难句分析模块',
							'3、新增考试大纲模块'
						]
					}, {
						id: 3,
						edition: 'v1.0.5',
						time: '2020/05/20',
						content: [
							'1、新增历年真题模块',
							'2、单词以轮播图形式展示',
							'3、完善关于界面'
						]
					},
					{
						id: 4,
						edition: 'v1.0.7',
						time: '2020/05/30',
						content: [
							'1、新增写作佳句模块',
							'2、新增答题技巧模块'
						]
					},
					{
						id: 5,
						edition: 'v1.1.3',
						time: '2020/06/08',
						content: [
							'1、优化细节'
						]
					},

				]
			}
		},
		onLoad() {},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	page {
		height: 100%;
		width: 100%;
		background-color: #f5f6f8;
	}

	.max {
		height: 100%;
		min-height: 100vh;
		background-color: #f5f6f8;
	}
</style>
