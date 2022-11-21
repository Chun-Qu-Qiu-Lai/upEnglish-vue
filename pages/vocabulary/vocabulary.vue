<template>
	<view class="max">
		<view class="uni-margin-wrap">
			<swiper class="swiper" style="height: 100vh;background-color: #e8e8e8;" circular
				:easing-function="easeInOutCubic" :indicator-dots="indicatorDots" :autoplay="autoplay"
				:interval="interval" :duration="duration">
				<swiper-item v-for="(item,index) in words" :key="index">
					<view class="swiper-item uni-bg-red" style="padding-top: 7vh;overflow: hidden;">
						<view
							style="width: 300rpx;height: 300rpx;border-radius: 50%;background-color: #e8e8e8;z-index: 100;margin-top: 230rpx;position: absolute;right: -50px;transform: rotateY(48deg);">
						</view>
						<image src="https://www.shanzs.top/lhbfile/tubiaos/shuji.png"
							style="width: 170rpx;height: 170rpx;float: right;z-index: 100;"></image>
						<view
							style="background-color: rgba(51, 125, 255,0.3);height: 20vh;border-radius: 20rpx;width: 96vw;margin: auto;padding-top: 40rpx;backdrop-filter: blur(15px)">
							<view style="font-size: 35px;text-align: center;color: #4d4d4d;letter-spacing: 0.1rem;">
								{{item.word}}
							</view>
							<view style="align-items: center;display: flex;justify-content: center;">
								<view
									style="text-align: center;margin-top: 50rpx;font-size: 15px;background-color: #ffedf3;display: inline;padding: 10rpx 10rpx 15rpx 15rpx;border-radius: 15rpx;color: #4d453d;">
									{{item.type}}{{item.wordTranslate}}
								</view>
							</view>
						</view>
						<view
							style="background-color:rgba(177, 149, 127,0.3);width: 87vw;margin:20vh auto;padding: 30rpx 30rpx ;border-radius: 20rpx;">
							<view style="font-size: 18px;line-height: 50rpx;">例句:{{item.exampleSentence}}</view>
							<view style="border: 1rpx #c7b39e solid;margin-top: 20rpx;"></view>
							<view style="font-size: 15px;letter-spacing: 0.1rem;line-height: 50rpx;">
								解释：{{item.sentenceTranslate}}</view>
						</view>
					</view>
				</swiper-item>
			</swiper>
		</view>
	</view>

</template>
<script>
	export default {
		data() {
			return {
				words: [{
					id: 1,
					word: 'acclaim',
					type: 'n.v.',
					wordTranslate: '欢呼，喝彩；称赞',
					exampleSentence: 'She has been acclaimed for the TV drama Prime Suspect.',
					sentenceTranslate: '她凭借电视剧《头号嫌疑犯》而受到好评。'

				}, {
					id: 2,
					word: 'addict',
					type: 'n.v.',
					wordTranslate: '使沉溺，使入迷；使成瘾',
					exampleSentence: "He's only 24 years old and a drug addict",
					sentenceTranslate: '他只有24岁，确是个瘾君子。'

				}, {
					id: 3,
					word: 'adore',
					type: 'v',
					wordTranslate: '崇拜，敬爱；爱慕；极喜爱',
					exampleSentence: 'She adored her parents and would do anything to please them',
					sentenceTranslate: '她很爱自己的父母，为让他们高兴愿意做任何事情。'

				}, {
					id: 4,
					word: 'advent',
					type: 'n.',
					wordTranslate: '尤指不寻常的人或事物的出现，到来',
					exampleSentence: 'She has been acclaimed for the TV drama Prime Suspect.',
					sentenceTranslate: '战争的到来使形势更为严峻。'

				}, {
					id: 5,
					word: 'affluent',
					type: 'a.',
					wordTranslate: '富裕的；丰富的；富饶的',
					exampleSentence: 'Cigaretee smoking used to be commoner among affluent people.',
					sentenceTranslate: '吸烟曾经在富人中间更为普遍。'
				}],
				current: 0,
				mode: 'round',
			}
		},
		methods: {
			change(e) {
				this.current = e.detail.current;
			}
		}
	}
</script>
<style lang="scss" scoped>
	/deep/.uni-swiper__dots-box {
		display: none !important;
	}



	page {
		height: 100vh;
		background-color: #e8e8e8;
	}

	.max {
		height: 100%;
	}

	.swiper-box {
		/* height: 100%; */
	}
</style>
