<template>
	<view class="flex">
		<view class="title">
			<text>button</text>
		</view>
		<view class="flex-item">
			<button type="primary">页面主操作 Normal</button>
			<button type="primary" loading>页面主操作 loading</button>
			<button type="primary" disabled>页面主操作 disabled</button>
			<button type="default">页面次要操作 Normal</button>
			<button type="default" disabled>页面次要操作 disabled</button>
			<button type="warn">警告类操作 Normal</button>
			<button type="warn" disabled>警告类操作 disabled</button>
		</view>
		<view class="flex-item mid">
			<button type="primary" plain>按钮</button>
			<button type="primary" plain disabled>不可点击按钮</button>
			<button type="default" plain>按钮</button>
			<button type="default" plain disabled>按钮</button>
		</view>
		<view class="flex-item">
			<button type="primary" size="mini">按钮</button>
			<button type="warn" size="mini">按钮</button>
			<button type="default" size="mini">按钮</button>
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
	button {
		margin: 20rpx 5px;
	}
	.mid {
		padding: 0 200rpx;
	}
</style>
