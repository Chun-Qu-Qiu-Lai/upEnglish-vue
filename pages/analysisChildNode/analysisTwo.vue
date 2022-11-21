<template>
	<view style="">
		<view
			style="font-size: 17px;width: 95vw;margin:5% auto;padding: 30rpx 30rpx;background-color: #eaeaea;font-style: italic;">
			It is not obvious how the capacity to visualize objects
			and to figure out numerical patterns suits one to
			answer questions that have eluded some of the best
			poets and philosophers.
		</view>
		<!--  -->
		<view class="lab">
			<view class="lab-icon">
			</view>
			<view class="lab-text">【词汇突破】</view>
		</view>
		<view style="display: flex;flex-direction:column;padding: 20rpx 30rpx 15rpx  30rpx;">
			<view>visualize想象
			</view>
			<view>Figure out 发现和找出</view>
		</view>
		<!--  -->
		<view class="lab">
			<view class="lab-icon">
			</view>
			<view class="lab-text">【主干识别】</view>
		</view>
		<view style="display: flex;flex-direction:column;padding: 20rpx 30rpx 15rpx  30rpx;">
			句子主语是由how引导的一个主语从句，it是句子的形式主语；句子主干为: How …is not
			obvious. 在主语从句中主语是capacity，谓语是suits 宾语是one；【其他成分】：状语为to
			answer。主语后加上两个动词不定式做后置定语；动词不定式中的宾语questions后面接一个that引导的定语从句。</view>
		<!--  -->
		<view class="lab">
			<view class="lab-icon">
			</view>

			<view class="lab-text">【难点揭秘】</view>
		</view>
		<view style="display: flex;flex-direction:column;padding: 20rpx 30rpx 15rpx  30rpx;">
			这个句子是一个由形式主语it引导的主语
			从句，其中难点为需要识别出主语从句中的动词suits.
		</view>
		<!--  -->
		<view class="lab">
			<view class="lab-icon">
			</view>
			<view class="lab-text">【译文赏析】</view>
		</view>
		<view style="display: flex;flex-direction:column;padding: 20rpx 30rpx 15rpx  30rpx;">
			构思物体和找出数字模型的能力是如何让一个人去回答那些连最好的诗人和哲学家都回避的问题
			的，这点我们还不是很清楚。</view>



	</view>
</template>

<script>
</script>

<style lang="scss">
	page {
		background-color: #f8f9fa;
		line-height: 50rpx;
	}

	.lab {
		display: flex;
		height: 70rpx;
		margin-top: 20rpx;
		background-color: azure;
		padding-left: 15rpx;
		align-items: center;

		.lab-icon {
			width: 10rpx;
			height: 60rpx;
			background-color: aqua;
			border-radius: 13rpx;
		}

		.lab-text {
			line-height: 70rpx;
			font-weight: bold
		}
	}
</style>
