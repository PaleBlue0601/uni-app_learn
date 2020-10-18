<template>
	<view>
		<scroll-view scroll-y="true" ref="content">
			<view class="content">
				<view class="list-item" v-for="(item, index) in listData" :key="index">
					<navigator :url="'../post/post'+'?index='+index">
						<image :src="item.imgurl"></image>
						<view class="item-title">
							{{item.title}}
						</view>
						<view class="item-tag">
							<text>{{item.count}}浏览</text>
						</view>
					</navigator>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				listData: [
					{
						imgurl: '../../static/list/list_1.jpg',
						title: '你为什么要买奥迪车?',
						count: 336
					},
					{
						imgurl: '../../static/list/list_2.jpg',
						title: '七夕活动:执子之手，以子偕老晒步数赢好礼',
						count: 1739
					},
					{
						imgurl: '../../static/list/list_3.jpg',
						title: '一盔一带:安全带打卡',
						count: 41633
					},
					{
						imgurl: '../../static/list/list_4.jpg',
						title: '有人跟你借车你会借吗?',
						count: 2361
					},
					{
						imgurl: '../../static/list/list_5.jpg',
						title: '老婆开车你敢做副驾驶吗?',
						count: 1765
					},
					{
						imgurl: '../../static/list/list_6.jpg',
						title: '这个五一很特别你在干啥?',
						count: 608
					}
				]
			}
		},
		created() {
			this.setScrollViewHeight()
		},
		methods: {
			// 根据设备适配.content的高度
			setScrollViewHeight() {
				let computeHeight
				uni.getSystemInfo({
					success(res) {
						// 根据设备高度计算后数值
						computeHeight = res.screenHeight - 94;
					}
				})
				this.$nextTick(() => {
					this.$refs.content.$el.style.height = computeHeight+'px'
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		justify-content: space-around;
		flex-direction: row;
		flex-wrap: wrap;
		background-color: #eee;
	}
	.content .list-item {
		width: 46%;
		height: 400rpx;
		background-color: #FFFFFF;
		position: relative;
		margin: 20rpx 0;
	}
	.list-item image {
		width: 100%;
		height: 240rpx;
	}
	.list-item .item-title {
		font-weight: bold;
		padding: 10rpx;
		font-size: 30rpx;
	}
	.list-item .item-tag {
		width: 100%;
		padding: 10rpx;
		box-sizing: border-box;
		position: absolute;
		bottom: 0;
		text-align: right;
	}
	.item-tag text {
		font-size: 24rpx;
		color: #CCCCCC;
	}
</style>
