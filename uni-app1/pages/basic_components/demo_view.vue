<template>
	<view class="flex">
		<view class="title">
			<text>view属性演示</text>
		</view>
		<view class="flex-item" hover-class="active">
			hover-class:指定按下去的样式类。
		</view>
		<view class="flex-item" hover-class="active">
			父节点
			<view hover-class="active" :hover-stop-propagation="true">
				hover-stop-propagation=true
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.active {
		font-size: 40rpx;
	}
	.flex-item {
		color: #333333;
		border: 1px solid #4CD964;
	}
</style>
