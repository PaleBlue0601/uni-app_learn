<template>
	<view>
		<scroll-view scroll-y="true" class="scroll-carlist">
			<view class="content">
				<view class="hotcar">
					<view class="hotcar-title">
						热门品牌
					</view>
					<view class="hotcar-list">
						<view class="hotcar-list_item" v-for="(item, index) in cars" :key="index" @click="selectBack(item.name)">
							<image :src="item.imgurl"></image>
							<view class="car_name">
								{{item.name}}
							</view>
						</view>
					</view>
				</view>
				<view class="allcars">
					<view class="allcars-item" v-for="(item1, index1) in chineseNum" :key="index1">
						<view class="allcars-item_title">
							{{item1}}
						</view>
						<view class="allcars-items" v-for="(item2, index2) in cars" :key="index2" @click="selectBack(item2.name)">
							<image :src="item2.imgurl"></image>
							<view class="car_name">
								{{item2.name}}
							</view>
						</view>
					</view>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				cars: [
					{
						imgurl: '../../static/carlist/ft.png',
						name: '丰田'
					},
					{
						imgurl: '../../static/carlist/rc.png',
						name: '日产'
					},
					{
						imgurl: '../../static/carlist/dz.png',
						name: '大众'
					},
					{
						imgurl: '../../static/carlist/ad.png',
						name: '奥迪'
					},
					{
						imgurl: '../../static/carlist/jl.png',
						name: '吉利'
					},
					{
						imgurl: '../../static/carlist/bk.png',
						name: '别克'
					},
					{
						imgurl: '../../static/carlist/bt.png',
						name: '本田'
					},
					{
						imgurl: '../../static/carlist/byd.png',
						name: '比亚迪'
					},
					{
						imgurl: '../../static/carlist/cc.png',
						name: '长城'
					},
					{
						imgurl: '../../static/carlist/xfl.png',
						name: '雪佛兰'
					}
				],
				chineseNum: ['一','二','三','四','五','六']
			}
		},
		methods: {
			// 返回上级页面并传递参数
			selectBack(name) {
				let pages = getCurrentPages();
				let prevPage = pages[pages.length - 2]; 
				prevPage.$vm.getCarname(name);//重点$vm
				uni.navigateBack()
			}
		}
	}
</script>

<style>
	.scroll-carlist {
		height: 623px;
	}
	.content {
		display: flex;
		flex-direction: column;
		justify-content: center;
		box-sizing: border-box;
		padding: 0 30rpx;
	}
	.hotcar-list {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
	}
	.hotcar .hotcar-title {
		box-sizing: border-box;
		padding: 30rpx 0;
		padding-left: 30rpx;
	}
	.hotcar-list .hotcar-list_item {
		width: 20%;
		height: 200rpx;
		text-align: center;
	}
	.hotcar-list_item image {
		width: 100rpx;
		height: 100rpx;
	}
	.hotcar-list_item .car_name {
		font-size: 20rpx;
	}
	.allcars {
		margin-left: -30rpx;
		margin-right: -30rpx;
	}
	.allcars .allcars-item_title {
		background-color: #EEEEEE;
		box-sizing: border-box;
		padding: 0 30rpx;
		font-size: 36rpx;
	}
	.allcars .allcars-items {
		height: 100rpx;
		display: flex;
		flex-direction: row;
		box-sizing: border-box;
		padding: 10rpx 30rpx;
		line-height: 80rpx;
		border-top: 1rpx solid #CCCCCC;
	}
	.allcars .allcars-items image {
		width: 80rpx;
		height: 80rpx;
		margin-right: 20rpx;
	}
</style>
