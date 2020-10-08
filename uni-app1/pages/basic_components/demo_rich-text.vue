<template>
	<view class="flex">
		<view class="flex-item">
			<view class="item-title">
				数组类型
				<text>\nnodes属性为Array</text>
			</view>
			<view class="arr-box">
				<rich-text :nodes="nodes"></rich-text>
			</view>
		</view>
		<view class="flex-item">
			<view class="item-title">
				字符串类型
				<text>\nnodes属性为String</text>
			</view>
			<view class="string-box">
				<rich-text :nodes="strings"></rich-text>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				nodes: [{
					name: 'div',
					attrs: {
						class: 'div-class',
						style: 'line-height: 80px; color: witch; text-align:center;'
					},
					children: [{
						type: 'text',
						text: '你好&nbsp;世界!'
					}]
				}],
				strings: '<div style="text-align:center;"><img src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/uni@2x.png"/></div>'
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.arr-box {
		margin: 20rpx 0;
		padding: 20rpx;
		height: 200rpx;
		background-color: #acacac;
	}
	.string-box {
		margin: 20rpx 0;
		padding: 20rpx;
		height: 250rpx;
		background-color: #d5d5d5;
	}
</style>
