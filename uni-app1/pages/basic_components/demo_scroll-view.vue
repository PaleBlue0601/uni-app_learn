<template>
	<view class="flex">
		<view class="title">
			<text>scroll-view,区域滚动视图</text>
		</view>
		<view class="flex-item">
			<view class="item-title">
				Vertical Scroll
				<text>\n纵向滚动</text>
			</view>
			<view>
				<scroll-view class="scroll-y" scroll-y="true" :scroll-top="scrollTop" @scroll="scroll">
					<view id="demo1" class="scroll-view-item">A</view>
					<view id="demo2" class="scroll-view-item">B</view>
					<view id="demo3" class="scroll-view-item">C</view>
				</scroll-view>
			</view>
			<view class="btn" @tap="goTop">
				点击这里返回顶部
			</view>
		</view>
		<view class="flex-item">
			<view class="item-title">
				Horizontal Scroll
				<text>\n横向滚动</text>
			</view>
			<view>
				<scroll-view class="scroll-h" scroll-x="true" @scroll="scroll" scroll-left="120">
					<view id="demo1" class="scroll-view-item">A</view>
					<view id="demo2" class="scroll-view-item">B</view>
					<view id="demo3" class="scroll-view-item">C</view>
				</scroll-view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				scrollTop: 0
			}
		},
		methods: {
			scroll: function (e) {
				// console.dir(e)
				this.scrollTop = e.detail.scrollTop
			},
			goTop: function(e) {
				// console.dir(e)
				// $nextTick 子组件完全挂载之后在执行操作
				this.$nextTick(function() {
					this.scrollTop = 0
				});
				uni.showToast({
					icon: "none",
					title: "纵向滚动 scrollTop 值已被修改为 0"
				})
			}
		}
	}
</script>

<style>
	.item-title {
		text-align: left;
		color: #333333;
		margin: 20rpx auto;
	}
	.item-title text {
		color: #888888;
		font-size: 15rpx;
	}
	.scroll-view-item {
		width: 100%;
		height: 300rpx;
		line-height: 300rpx;
		text-align: center;
		color: #FFFFFF;
	}
	.scroll-y {
		height: 300rpx;
		width: 100%;
	}
	.scroll-h {
		height: 329rpx;
		width: 100%;
		white-space: nowrap;
	}
	.scroll-h .scroll-view-item {
		display: inline-block;
	}
	#demo1 {
		background-color: #0000FF;
	}
	#demo2 {
		background-color: #ff0000;
	}
	#demo3 {
		background-color: #00aa00;
	}
	.btn {
		color: #333333;
		font-size: 1em;
		margin-top: 20rpx;
	}
</style>
