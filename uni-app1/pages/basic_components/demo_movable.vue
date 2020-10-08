<template>
	<view class="flex">
		<view class="flex-item">
			<view class="item-title">
				示例 1
				<text>\nmovable-view 区域小于 movable-area</text>
			</view>
			<movable-area>
				<movable-view :x="x" :y="y" @change="onChange" direction="all">
					text
				</movable-view>
			</movable-area>
			<view @tap="tap" class="btn">
				点击这里移动至 (30px, 30px)
			</view>
		</view>
		<view class="flex-item">
			<view class="item-title">
				示例 2
				<text>\nmovable-view 区域大于 movable-area</text>
			</view>
			<movable-area>
				<movable-view class="movable-view-max" direction="all">
					text
				</movable-view>
			</movable-area>
		</view>
		<view class="flex-item">
			<view class="item-title">
				示例 3
				<text>\n只可以横向移动</text>
			</view>
			<movable-area>
				<movable-view direction="horizontal">
					text
				</movable-view>
			</movable-area>
		</view>
		<view class="flex-item">
			<view class="item-title">
				示例 4
				<text>\n只可以纵向移动</text>
			</view>
			<movable-area>
				<movable-view direction="vertical">
					text
				</movable-view>
			</movable-area>
		</view>
		<view class="flex-item">
			<view class="item-title">
				示例 5
				<text>\n可超出边界</text>
			</view>
			<movable-area>
				<movable-view direction="all" out-of-bounds>
					text
				</movable-view>
			</movable-area>
		</view>
		<view class="flex-item">
			<view class="item-title">
				示例 5
				<text>\n带有惯性</text>
			</view>
			<movable-area>
				<movable-view direction="all" inertia>
					text
				</movable-view>
			</movable-area>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				x: 0,
				y: 0
			}
		},
		methods: {
			onChange(e) {
				this.x = e.detail.x
				this.y = e.detail.y
			},
			tap() {
				this.x = 30
				this.y = 30
			}
		}
	}
</script>

<style>
	.btn {
		margin-top: 20rpx;
	}
	movable-area {
		width: 100%;
		height: 300rpx;
		background-color: #a1a1a1;
		overflow: hidden;
	}
	movable-view {
		display: block;
		text-align: center;
		line-height: 100rpx;
		color: #FFFFFF;
		width: 100rpx;
		height: 100rpx;
		background-color: #0000FF;
	}
	.movable-view-max {
		width: 400rpx;
		height: 400rpx;
		line-height: 400rpx;
	}
</style>
