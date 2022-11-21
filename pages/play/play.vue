<template>
	<view>
		<uni-popup ref="popup" type="dialog">
			<uni-popup-dialog message="成功消息" :duration="2000" :before-close="true" @close="close" @confirm="confirm">
				<view style="display: flex;flex-direction: column;">
					<view>
						<uni-datetime-picker v-model="form.range" type="daterange" @maskClick="maskClick" />
					</view>
					<input placeholder="我的计划" v-model="form.myPlay" />
				</view>
			</uni-popup-dialog>
		</uni-popup>
		<view
			style="margin: auto;background-color: #e8e8e8;font-size: 20px;text-align: center;letter-spacing: 0.1rem;line-height: 80rpx;color: #5d5d43;font-weight: bolder">
			计划清单</view>
		<view style="background-color: #e8e8e8;width: 95vw;margin: 40rpx auto;padding: 20rpx 10rpx;"
			v-for="item in list" :key="item.id">
			<view
				style="display: flex;text-align: center;align-items: center;background-color: #f1f1f1;border-radius: 20rpx;">
				<view style="font-size: 19px;">开始时间：</view>
				<view>{{item.range[0]}}</view>
			</view>
			<view style="display: flex;text-align: center;align-items: center;background-color: #f1f1f1;margin-top: 40rpx;
		">
				<view style="font-size: 19px;">截止时间：</view>
				<view>{{item.range[1]}}</view>
			</view>
			<view
				style="display: flex;text-align: center;align-items: center;background-color: #f1f1f1;margin-top: 40rpx;font-size: 19px;">
				<view> 待做计划：</view>
				<view>{{item.myPlay}}</view>
			</view>
		</view>

		<view>
			<button
				style="position: absolute;bottom: 0rpx;width: 100%;	background-color: rgba(119, 175, 119, 1);color: aliceblue;letter-spacing: 0.1rem;"
				@click="openDig()">添加计划</button>
		</view>

	</view>

</template>

<script>
	export default {
		data() {
			return {
				list: [{
					id: 1,
					range: ['2020-11-27 08:45', '2020-11-27 09:45'],
					myPlay: '背20个单词'
				}, {
					id: 2,
					range: ['2020-11-27 10:25', '2020-11-27 11:30'],
					myPlay: '做两个阅读题'
				}, {
					id: 3,
					range: ['2020-11-27 15:12', '2020-11-27 17:15'],
					myPlay: '复习昨天的知识'
				}, ],
				form: {
					id: null,
					range: [],
					myPlay: ''
				}
			}
		},
		methods: {
			openDig() {
				this.$refs.popup.open()
			},

			close() {
				this.$refs.popup.close()
			},

			confirm(value) {
				var len = this.list.length + 1;
				this.form.id = len;
				this.list.push(this.form);
				this.$refs.popup.close()
			}
		}
	}
</script>

<style>
	page {
		background-color: #f8f9fa;
	}
</style>
