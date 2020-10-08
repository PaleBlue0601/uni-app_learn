<template>
	<view class="flex">
		<view class="title">
			<text>text</text>
		</view>
		<view class="flex-item">
			<text selectable>设置文字可选</text>
		</view>
		<view class="flex-item">
			<text space="ensp">设置space:ensp Hello</text>
		</view>
		<view class="flex-item">
			<text space="emsp">设置space:emsp Hello</text>
		</view>
		<view class="flex-item">
			<!-- 空格大小根据字体大小变化 -->
			<text class="text-nbsp" space="nbsp">设置space:nbsp Hello</text>
		</view>
		<!-- #ifndef H5 || MP-WEIXIN || APP-PLUS -->
		<view class="flex-item">
			<text decode="false">未设置设置解码&nbsp;&lt;</text>
		</view>
		<!-- #endif -->
		<view class="flex-item">
			<text decode>设置解码&nbsp;&lt;</text>
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
	.text-nbsp {
		font-size: 50rpx;
	}
</style>
