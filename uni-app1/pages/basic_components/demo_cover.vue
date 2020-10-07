<template>
	<view class="flex">
		<view class="title">
			<text>cover-view用于覆盖map,vide等原生组件</text>
		</view>
		<view class="flex-item">
			<map style="width: 100%; height: 300px;" :latitude="latitude" :longitude="longitude" :markers="covers">
				<cover-view>简单的自定义 controls</cover-view>
				<cover-image class="img" src="../../static/logo.png" mode=""></cover-image>
			</map>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				id:0, // 使用 marker点击事件 需要填写id
				title: 'map',
				latitude: 39.909,
				longitude: 116.39742,
				covers: [{
						latitude: 39.909,
						longitude: 116.39742,
						iconPath: '../../../static/logo.png'
				}, {
						latitude: 39.90,
						longitude: 116.39,
						iconPath: '../../../static/logo.png'
				}]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.img {
		width: 200rpx;
		height: 200rpx;
		margin: 100rpx auto;
	}
</style>
