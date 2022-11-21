<template>
	<!-- 
	 this.screenHeight = uni.getSystemInfoSync().windowHeight+"px"
	 :style="{ height: screenHeight }" 
	 -->
	<view class="max">
		<view style="background-color: rgba(241, 244, 251, 0.3);display: flex;flex-direction: column;height: 340rpx;">
			<view class="max_circular"
				style="width: 190rpx;height: 190rpx;border-radius: 50%;margin: auto;background-color: #fff;align-items: center;display: flex;">
				<view class="min_circular" style="width: 160rpx;height: 160rpx;border-radius: 50%;margin: auto;">
					<image :src="avatarUrl" style="width: 160rpx;height: 160rpx;border-radius: 50%;">
					</image>
				</view>
			</view>
			<view style="margin: auto;font-size: 1.4rem;font-weight: 200;" v-show="isAuth">{{nickName}}</view>
			<button style="background-color:rgb(241, 244, 251);" v-show="!isAuth" @click="toAuth()">授权登录</button>
		</view>
		<!-- 功能列表 -->
		<view class="set_list">
			<view style="display: flex;align-items: center;height: 80rpx;">
				<view style="">
					<image :src="personalIcon" style="width: 80rpx;height: 80rpx;transform: scale(0.7);"></image>
				</view>
				<view class="list">
					<button open-type="share" class="shareBtn"
						style="border-radius: 0rpx;border:none;background-color: #fff;line-height: 80rpx;font-weight: lighter;display: block;text-align: left;font-size: 0.9rem;margin-left: 0rpx;padding-left: 0%;">分享好友</button>
				</view>
			</view>
			<view style="display: flex;align-items: center;height: 80rpx;">
				<view style="">
					<image :src="feedIcon" style="width: 80rpx;height: 80rpx;">
					</image>
				</view>
				<view class="list" @click="toFeedMessage()">
					意见反馈
				</view>
			</view>
			<view style="display: flex;align-items: center;height: 80rpx;">
				<view style="">
					<image :src="with_meIcon" style="width: 80rpx;height: 80rpx;transform: scale(0.7);"></image>
				</view>
				<view class="list" @click="withMe()">
					联系我们
				</view>
			</view>
			<view style="display: flex;align-items: center;height: 80rpx;">
				<view style="">
					<image :src="messageIcon" style="width: 80rpx;height: 80rpx;transform: scale(0.7);"></image>
				</view>
				<view class="list" @click="toLookMessage()">
					更新日志
				</view>
			</view>
			<view style="display: flex;align-items: center;height: 80rpx;">
				<view style="">
					<image :src="login_outIcon" style="width: 80rpx;height: 80rpx;transform: scale(0.6);"></image>
				</view>
				<view class="list" @click="toLoginOut()">
					注销登录
				</view>
			</view>
		</view>
		<!-- 退出确认框 -->
		<uni-popup ref="popup" type="dialog">
			<uni-popup-dialog mode="input" message="成功消息" :duration="2000" :before-close="true" @close="close"
				@confirm="confirm"></uni-popup-dialog>
		</uni-popup>

	</view>
</template>

<script>
	import requestUrl from "../../api/request.js"
	export default {
		data() {
			return {
				code: null,
				isAuth: false,
				nickName: null,
				avatarUrl: null,

				personalIcon: null,
				feedIcon: null,
				with_meIcon: null,
				messageIcon: null,
				login_outIcon: null,
			}
		},
		onLoad() {
			this.personalIcon = this.$store.state.icon.personalIcon;
			this.feedIcon = this.$store.state.icon.feedIcon;
			this.with_meIcon = this.$store.state.icon.with_meIcon;
			this.messageIcon = this.$store.state.icon.messageIcon;
			this.login_outIcon = this.$store.state.icon.login_outIcon;

			this.isAuth = true;
			this.avatarUrl ="https://www.shanzs.top/lhbfile/touxiang.png";
			this.nickName = "苹果树"

			// uni.login({
			// 	provider: "weixin",
			// 	success: (res) => {
			// 		this.code = res.code
			// 		uni.request({
			// 			url: requestUrl.prod.BASE_URL + "/cetapp/user/getUserInfo",
			// 			method: "GET",
			// 			header: {
			// 				"Authorization": wx.getStorageSync("token")
			// 			},
			// 			success: (res) => {
			// 				if (res.data.code == 200) {
			// 					this.isAuth = true;
			// 					this.avatarUrl = res.data.data.userInfo.avatarUrl;
			// 					this.nickName = res.data.data.userInfo.nickName;
			// 				} else {
			// 					this.isAuth = false;
			// 				}
			// 			}
			// 		})
			// 	}
			// })
		},

		methods: {
			openLogin() {

			},
			shuaxin() {

			},
			onChooseAvatar(e) {
				const {
					avatarUrl
				} = e.detail
				this.setData({
					avatarUrl,
				})
			},
			toAuth() {

			},
			share() {
				wx.showShareMenu({
					withShareTicket: true,
					menus: ['shareAppMessage', 'shareTimeline']
				})
			},
			toLookMessage() {
				uni.navigateTo({
					url: "/pages/message/index"
				})
			},
			toFeedMessage() {
				uni.navigateTo({
					url: "/pages/feed/index"
				})
			},
			withMe() {
				uni.navigateTo({
					url: "/pages/withme/index"
				})
			},
			toLoginOut() {
				/* 	this.isAuth = false;
					this.avatarUrl = null
					this.nickName = null */
			},
			open() {
				this.$refs.popup.open()
			},
			close() {
				this.$refs.popup.close()
			},
			confirm(value) {
				this.$refs.popup.close()
			}
		}
	}
</script>


<style lang="scss" scoped>
	.shareBtn::after {
		border: none;
	}

	.max {
		height: 100%;
		background: linear-gradient(to bottom, rgb(152, 206, 231), #FFFFFF);
	}

	page {
		height: 100%;
		width: 100%;
	}

	.login {
		background-color: rgb(235, 217, 193);
		bottom: 0rpx;
		width: 20%;
		padding: 0rpx 1% 0rpx 1%;
		text-align: center;
		font-family: "楷体";
		font-size: 0.6rem;
	}


	.list {
		font-size: 0.9rem;
		font-family: Cambria, Cochin, Georgia, Times, ‘Times New Roman’, serif;
		width: 100%;
		height: 100%;
		border-bottom: 2rpx #d9dad5 solid;
		padding-left: 4%;
		line-height: 80rpx;
		font-weight: lighter;
	}

	.set_list {
		background-color: #fff;
		width: 90%;
		margin: auto;
		padding: 10rpx 0rpx;
		margin-top: 200rpx;
		border-radius: 20rpx;
		box-shadow: -10px 10px 10px rgba(0, 0, 0, 0.1);
		font-weight: bold;
	}
</style>
