<template>
	<view class="content">
		<view class="item">
			1
		</view>
		<view class="item">
			2
		</view>
		<view class="item">
			3
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

<style scoped>
	.content {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
	}
	.item {
		background-color: #57d99f;
		text-align: center;
		font-size: 40rpx;
		height: 100rpx;
		line-height: 100rpx;
		color: #757575;
		flex: 0 1 400rpx;
		margin: 5px;
	}
</style>
