<template>
	<view class="max" :style="{ height: screenHeight }">
		<uni-swiper-dot :info="info" :current="current" field="content" :mode="mode" dotsStyles="">
			<swiper class="swiper-box" @change="change" style="height: 30vh;overflow: auto;">
				<swiper-item v-for="(item ,index) in info" :key="index" style="height: 30vh;">
					<view class="swiper-item"
						style="display: flex;align-items: center;text-align: center;height: 25vh;overflow: auto;">
						<image :src="item.content"
							style="display: flex;align-items: center;text-align: center;width: 100%;height: 25vh;">
						</image>
					</view>
				</swiper-item>
			</swiper>
		</uni-swiper-dot>
		<!-- 		<swiper-item>
				<view class="swiper-item">
					<scroll-view scroll-y="true" >
						<view class="box" style="height: 20vh;">
							<view >
								这里是内容
							</view>
						</view>
					</scroll-view>
				</view>
			</swiper-item> -->

		<view
			style="height: 50vh;background: linear-gradient(to bottom, #2bcbeb, #FFFFFF);border-top-right-radius: 38rpx;border-top-left-radius:38rpx ;padding-top: 90rpx;margin-top: -7vh;">
			<!--3  -->
			<view class="mainLabOne">
				<view class="itemList" @click="toPlay()">
					<view class="itemList-img">
						<image src="https://www.shanzs.top/lhbfile/tubiaos/jihua.png"
							style="width: 50rpx;height: 50rpx;">
						</image>
					</view>
					<view>我的计划</view>
				</view>
				<view class="itemList" @click="toStudyData()">
					<view class="itemList-img">
						<image src="https://www.shanzs.top/lhbfile/tubiaos/shuju.png"
							style="width: 50rpx;height: 50rpx;">
						</image>
					</view>
					<view>学习数据</view>
				</view>
				<view class="itemList" @click="signIn()">
					<view class="itemList-img">
						<image src="https://www.shanzs.top/lhbfile/tubiaos/qiandao.png"
							style="width: 50rpx;height: 50rpx;">
						</image>
					</view>
					<view>签到</view>
				</view>
			</view>
			<!--  线条-->
			<view style="width: 95vw;border-top: #FFFFFF 2rpx solid;margin: auto; margin-top: 3vh;"></view>

			<!-- 9 -->
			<view class="mainLabTwo">
				<view style="display: flex;flex-direction: row;justify-content: space-around;height: 10vh;">
					<view style="display: flex;justify-content: space-around;flex-direction: column;height: 100%;"
						@click="toVocabulary()">
						<view style="justify-content: center;display: flex;">
							<image src="https://www.shanzs.top/lhbfile/tubiaos/words.png"
								style="width: 50rpx;height: 50rpx;"></image>
						</view>
						<view>
							词汇训练
						</view>
					</view>
					<view style="display: flex;justify-content: space-around;flex-direction: column;height: 100%;"
						@click="toAnalysis()">
						<view style="justify-content: center;display: flex;">
							<image src="https://www.shanzs.top/lhbfile/tubiaos/fenxi.png"
								style="width: 50rpx;height: 50rpx;"></image>
						</view>
						<view>
							难句分析
						</view>
					</view>
					<view style="display: flex;justify-content: space-around;flex-direction: column;height: 100%;"
						@click="toComposition()">
						<view style="justify-content: center;display: flex;">
							<image src="https://www.shanzs.top/lhbfile/tubiaos/writing.png"
								style="width: 50rpx;height: 50rpx;"></image>
						</view>
						<view>
							写作佳句
						</view>
					</view>
				</view>

				<view style="display: flex;flex-direction: row;justify-content: space-around;height: 10vh;">
					<view style="display: flex;justify-content: space-around;flex-direction: column;height: 100%;"
						@click="toZhenti()">
						<view style="justify-content: center;display: flex;">
							<image src="https://www.shanzs.top/lhbfile/tubiaos/shijuan.png"
								style="width: 50rpx;height: 50rpx;"></image>
						</view>
						<view>
							历年真题
						</view>
					</view>
					<view style="display: flex;justify-content: space-around;flex-direction: column;height: 100%;"
						@click="toSkill()">
						<view style="justify-content: center;display: flex;">
							<image src="https://www.shanzs.top/lhbfile/tubiaos/papers.png"
								style="width: 50rpx;height: 50rpx;"></image>
						</view>
						<view>
							答题技巧
						</view>
					</view>
					<view style="display: flex;justify-content: space-around;flex-direction: column;height: 100%;"
						@click="toDagang()">
						<view style="justify-content: center;display: flex;">
							<image src="https://www.shanzs.top/lhbfile/tubiaos/enjoy.png"
								style="width: 50rpx;height: 50rpx;"></image>
						</view>
						<view>
							考试大纲
						</view>
					</view>
				</view>
			</view>
		</view>


	</view>

</template>

<script>
	import requestUrl from "../../api/request.js"
	export default {
		data() {
			return {
				info: [{
					content: 'https://www.shanzs.top/lhbfile/tubiaos/mapOne.png'
				}, {
					content: 'https://www.shanzs.top/lhbfile/tubiaos/mapTwo.png'
				}, {
					content: 'https://www.shanzs.top/lhbfile/tubiaos/mapThree.png'
				}],
				current: 0,
				mode: 'round',
			}
		},
		onLoad() {},
		methods: {

			change(e) {
				this.current = e.detail.current;
			},
			toAnalysis() {
				uni.navigateTo({
					url: "/pages/analysis/analysis"
				})
			},
			toVocabulary() {
				uni.navigateTo({
					url: "/pages/vocabulary/vocabulary"
				})
			},
			toComposition() {
				uni.navigateTo({
					url: "/pages/composition/composition"
				})
			},
			toStudyData() {
				uni.navigateTo({
					url: "/pages/studyData/studyData"
				})
			},
			toSkill() {
				uni.navigateTo({
					url: "/pages/skill/skill"
				})
			},
			toDagang() {
				uni.navigateTo({
					url: "/pages/dagang/dagang"
				})
			},
			toZhenti() {
				uni.navigateTo({
					url: "/pages/zhenti/zhenti"
				})
			},
			toPlay() {
				uni.navigateTo({
					url: "/pages/play/play"
				})
			},
			signIn() {
				uni.showToast({
					title: "签到成功",
					icon: 'success',
					duration: 2000
				});
				/* 	uni.login({
						provider: "weixin",
						success: (res) => {
							this.code = res.code
							uni.request({
								url: requestUrl.prod.BASE_URL + "/cetapp/user/sign_in",
								method: "GET",
								header: {
									"Authorization": wx.getStorageSync("token")
								},
								success: (res) => {
									if (res.data.code == 200) {
										uni.showToast({
											title: res.data.msg,
											icon: 'success',
											duration: 2000
										});
									} else {
										uni.showToast({
											title: '请先登录',
											icon: 'error',
											duration: 2000
										});
									}
								}
							})
						}
					}) */
			}
		}
	}
</script>

<style lang="scss">
	.max {
		/* 	background: url(https://www.shanzs.top/svg/back.png);
		background-size: 100%; */
		/* padding-top: 5.6%; */
		height: 100%;
	}

	page {
		height: 100%;
		width: 100%;
	}

	* {
		font-family: "楷体";
	}

	.mainLabOne {
		width: 90vw;
		background-color: aliceblue;
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		height: 10vh;
		margin: auto;
		align-items: center;
		border-radius: 10rpx;
		font-size: 13px;
		color: #646464;

		.itemList {
			display: flex;
			justify-content: space-around;
			flex-direction: column;
			height: 100%;

			.itemList-img {
				justify-content: center;
				display: flex;
			}
		}
	}

	.mainLabTwo {
		box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.3);
		display: flex;
		flex-direction: column;
		height: 30vh;
		justify-content: space-around;
		background-color: azure;
		width: 90vw;
		margin: 20rpx auto;
		border-radius: 20rpx;
		font-size: 15px;
		color: #707070;
	}
</style>
