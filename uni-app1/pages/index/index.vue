<template>
	<view class="flex">
		<text class="flex-item name">whbHorse</text>
		<image class="flex-item" src="/static/user.jpg"></image>
		<navigator class="flex-item" url="../map/map">
			<text>{{content}}</text>
		</navigator>
		<navigator class="flex-item" url="../layout/index">
			<text>布局</text>
		</navigator>
		<navigator class="flex-item" url="../basic_components/index">
			<text>基础组件</text>
		</navigator>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				content: '地图组件'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.name {
		font-size: 40rpx;
		font-weight: bold;
		color: #333333;
	}
</style>
