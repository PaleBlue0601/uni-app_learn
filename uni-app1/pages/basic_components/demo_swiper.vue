<template>
	<view class="flex">
		<view class="title">
			<text>swiper,可滑动视图</text>
		</view>
		<view class="flex-item">
			<swiper :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration" circular>
				<swiper-item>
					<view class="swiper-item blue">1</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item red">2</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item green">3</view>
				</swiper-item>
			</swiper>
		</view>
		<view class="flex-item">
			<text :class="classList[0]" @click="changeIndicatorDots">{{indicatorDotsText}}</text>
			<text :class="classList[1]" @click="changeAutoplay">{{autoplayText}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				indicatorDots: true, //是否显示面板指示点
				autoplay: true, //是否自动切换
				interval: 2000, //自动切换时间间隔
				duration: 500, //滑动动画时长
				contentText: {
					indicatorDotsText: '点击关闭指示点',
					autoplayText: '点击关闭自动播放'
				},
				classList: [
					{
						'swiper-btn': true,
						active: false
					},
					{
						'swiper-btn': true,
						active: false
					}
				]
			}
		},
		methods: {
			changeIndicatorDots() {
				this.indicatorDots = !this.indicatorDots
				if(!this.indicatorDots) {
					this.contentText.indicatorDotsText = "点击开启指示点"
					this.classList[0].active = true
				} else {
					this.contentText.indicatorDotsText = "点击关闭指示点"
					this.classList[0].active = false
				}
			},
			changeAutoplay() {
					this.autoplay = !this.autoplay
					if(!this.autoplay) {
						this.contentText.autoplayText = '点击开启自动播放'
						this.classList[1].active = true
					} else {
						this.contentText.autoplayText = '点击关闭自动播放'
						this.classList[1].active = false
					}
			}
		},
		computed: {
			indicatorDotsText() {
				return this.contentText.indicatorDotsText
			},
			autoplayText() {
				return this.contentText.autoplayText
			},
		}
	}
</script>

<style>
	.swiper-item {
		line-height: 300rpx;
		color: #FFFFFF;
	}
	.blue {
		background-color: #0000FF;
	}
	.red {
		background-color: #FF0000;
	}
	.green {
		background-color: #00AA00;
	}
	.swiper-btn {
		display: block;
		margin: 10px;
	}
	.active {
		color: #333333;
	}
</style>
