<template>
	<view style="padding-top: 30rpx;">
		<view v-for="item in list" :key="item.id" style="width: 95vw;
			margin:20rpx auto;
			display: flex;
			flex-direction: row;
			height: 15vh;
			justify-content: space-between;
			border-radius: 10px;
			border: 1rpx #9ff19a solid;" @click="toReadContent(item.id)">
			<!-- 左 -->
			<view style="
				background: linear-gradient(to bottom, rgb(230, 249, 253), #FFFFFF);
				width: 65%;display: flex;
				flex-direction: column;
				justify-content: space-between;">
				<view style="color: #30d1df;
				text-align: center;
				font-size: 18px;
				background-color: #ffca01;
				box-shadow: 10rpx 10rpx 5rpx #fe7b21;
				width: 95%;
				margin: 10% auto;
				border: 3rpx #000000 solid;
				">
					{{item.title}}
				</view>
				<view style="display: flex;
				justify-content: space-between;
			background: linear-gradient(to bottom, rgb(230, 249, 253), #FFFFFF);">
					<view style="display: flex;align-items: center;border-bottom-left-radius:10px;">
						<image src="https://www.shanzs.top/lhbfile/tubiaos/yanjing.png"
							style="width: 55rpx;height: 55rpx;"></image>
						<view style="font-size: 15px;color: #635f4c;">{{item.readCount}}</view>
					</view>
					<view style="display: flex;align-items: center;">
						<image src="https://www.shanzs.top/lhbfile/tubiaos/shijian.png"
							style="width: 40rpx;height: 40rpx;"></image>
						<view style="font-size: 15px;color: #635f4c;">{{item.time}}</view>
					</view>
				</view>
			</view>
			<!-- 右 -->
			<image :src="item.pngSrc"
				style="width: 40%;height: 100%;border-top-right-radius:10px;border-bottom-right-radius:10px; ">
			</image>
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
						title: '大学生如何规划英语学习',
						time: '2021-05-11',
						readCount: 340,
						pngSrc: 'https://www.shanzs.top/lhbfile/tubiaos/readlist1.png'
					},
					{
						id: 2,
						title: '写作提高',
						time: '2012-05-21',
						readCount: 124,
						pngSrc: 'https://www.shanzs.top/lhbfile/tubiaos/readlist2.png'
					}, {
						id: 3,
						title: '如何定制适合自己的学习计划',
						time: '2021-08-03',
						readCount: 36,
						pngSrc: 'https://www.shanzs.top/lhbfile/tubiaos/readlist3.png'
					}, {
						id: 4,
						title: '如何说一口流利的英语',
						time: '2021-10-02',
						readCount: 14,
						pngSrc: 'https://www.shanzs.top/lhbfile/tubiaos/readlist4.png'
					}, {
						id: 5,
						title: '成为进阶英专生',
						time: '2021-12-28',
						readCount: 424,
						pngSrc: 'https://www.shanzs.top/lhbfile/tubiaos/readlist5.png'
					}, {
						id: 6,
						title: '刊外简单阅读',
						time: '2022-1-19',
						readCount: 24,
						pngSrc: 'https://www.shanzs.top/lhbfile/tubiaos/readlist6.png'
					}, {
						id: 7,
						title: '如何用碎片时间学习英语',
						time: '2022-8-14',
						readCount: 34,
						pngSrc: 'https://www.shanzs.top/lhbfile/tubiaos/readlist7.png'
					}, {
						id: 8,
						title: '高分指南',
						time: '2022-09-24',
						readCount: 34,
						pngSrc: 'https://www.shanzs.top/lhbfile/tubiaos/readlist8.png'
					}
				]
			}
		},
		methods: {
			toReadContent(id) {
				switch (id) {
					case 1:
						uni.navigateTo({
							url: "/pages/readContent/readOne"
						})
						break
					case 2:
						uni.navigateTo({
							url: "/pages/readContent/readTwo"
						})
						break
				}
			}
		}
	}
</script>

<style>
	page {
		background-color: #f5f5f5;
	}
</style>
