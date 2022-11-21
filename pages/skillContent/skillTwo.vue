<template>

	<view style="width: 96vw;margin: auto;padding-top: 40rpx;padding-bottom: 40rpx;">

		<view style="display: flex;align-items: center;margin-top: 89rpx;">
			<view
				style="width: 50rpx;height: 50rpx;border-radius: 50%;background-color: #e92163;	box-shadow:0px 0px 0px 5px rgba(233, 33, 99, 0.3);">
			</view>
			<view
				style="text-align: center;align-items: center;font-size: 19px;letter-spacing: 0.1rem;color: #e86e8b;font-weight: bold;margin-left: 30rpx;">
				一个中心，牢记心中</view>
		</view>

		<view style="margin-top: 74rpx;font-size: 16px">
			做阅读题时要从整体把握，阅读每一段的中心句，找出这个中心句的关键词。解题时要谨记文章的中心主旨和各段落的大意，其实阅读理解考的就是这个“中心句”。</view>


		<view style="display: flex;align-items: center;margin-top: 89rpx;">
			<view
				style="width: 50rpx;height: 50rpx;border-radius: 50%;background-color: #e92163;	box-shadow:0px 0px 0px 5px rgba(233, 33, 99, 0.3);">
			</view>
			<view
				style="text-align: center;align-items: center;font-size: 19px;letter-spacing: 0.1rem;color: #e86e8b;font-weight: bold;margin-left: 30rpx;">
				按序出题，迅速定位</view>
		</view>

		<view style="margin-top: 74rpx;font-size: 16px">
			每一个问题在原文中都要有一个定位，而且命题人是按顺序出题的。如果你认为不是，很有可能就是你做错了。文章基本以5段为主（也有6段、7段的），要把握每段之间的关系。一般来说，一段一个题，只是一般来说哦。
		</view>
		<view style="display: flex;align-items: center;margin-top: 89rpx;">
			<view
				style="width: 50rpx;height: 50rpx;border-radius: 50%;background-color: #e92163;	box-shadow:0px 0px 0px 5px rgba(233, 33, 99, 0.3);">
			</view>
			<view
				style="text-align: center;align-items: center;font-size: 19px;letter-spacing: 0.1rem;color: #e86e8b;font-weight: bold;margin-left: 30rpx;">
				干扰设置，常规排除</view>
		</view>

		<view style="margin-top: 74rpx;font-size: 16px" v-for="item in list" :key="item.id">
			<view>
				<view
					style="display: inline;padding: 8rpx 16rpx;background: rgba(233,33,99,1);color: #fff;border-radius: 16rpx;box-shadow: 0 0 0 3px rgb(233 33 99 / 30%);">
					{{item.id}}
				</view>
				<view style="margin-top: 36rpx;color: #6c6c6d;">
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
						content: '原句重复出现，一般为干扰项。正确的都是有改动的，即同义替换'
					},
					{
						id: 2,
						content: '选项中意思完全相反的2个选项，其中之一是对的'
					},
					{
						id: 3,
						content: '原文中很短、起过渡作用的句子出现在选择中，一般是干扰项'
					},
					{
						id: 4,
						content: '选项中的几个单词，是该段中不同句子里的单词拼凑的，一般是干扰项'
					},
					{
						id: 5,
						content: '错误的选项，往往是就文章某一方面而说的，其特点是：所涉及的，仅仅是某一个小问题，或者很具体，非常具体的一件实事。正确选项反应的，往往是实质的、根本的内容'
					},

					{
						id: 6,
						content: '一定要注意，谁是用来修饰谁的。起修饰作用的词或句子，来做选项，一般是错的。被修饰的那部分来作选项，一般是对的'
					},
					{
						id: 7,
						content: '说明原因的，且仅仅是说明原因而已，一般是干扰项'
					}
				]
			}
		}
	}
</script>

<style>
	* {
		line-height: 50rpx;
		
	}

	page {
		background-color: aliceblue;
			background-color: #f8f9fa;
	}
</style>
