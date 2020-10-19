<template>
	<view>
		<!-- 自定义导航栏 -->
		<uni-nav-bar>
			<view class="nav-title">
				<image src="../../static/logo.png" mode=""></image>
				<text>大连车事儿</text>
			</view>
			<view class="nav-left" slot="left">
				大连市<i class="fa fa-angle-down" aria-hidden="true"></i>
			</view>
			<view class="nav-right" slot="right">
				<i class="fa fa-search" aria-hidden="true"></i>
				<i class="fa fa-bell-o" aria-hidden="true"></i>
			</view>
		</uni-nav-bar>
		<scroll-view class="content" scroll-y="true" ref="content">
			<!-- item容器 -->
			<view class="card-item">
				<!-- 轮播图 -->
				<swiper class="branner" :indicator-dots="true" :autoplay="true" circular :interval="3000" :duration="1000">
					<swiper-item>
						<view class="swiper-item"><image src="../../static/branner_1.png"></image></view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item"><image src="../../static/branner_2.png" mode=""></image></view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item"><image src="../../static/branner_3.png" mode=""></image></view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item"><image src="../../static/branner_4.png" mode=""></image></view>
					</swiper-item>
				</swiper>
				<view class="row-list1">
					<view class="list-item" v-for="(item, index) in item_list1" :key="index">
						<i :class="iconClass(item.className)" aria-hidden="true"></i>
						<text>{{item.text}}</text>
					</view>
				</view>
				<view class="row-list2">
					<view class="list-item" v-for="(item,index) in item_list2" :key="index">
						<image :src="item"></image>
					</view>
				</view>
				<view class="row-posts">
					<view class="item-post">
						<view class="post-title">
							事发泉水！楼上直播唱歌数月 楼下业主崩溃了
						</view>
						<view class="post-info">
							<text class="info-tag1">#热点#</text>
							<text class="info-tag2">2983人浏览</text>
						</view>
					</view>
					<view class="item-post">
						<view class="post-title">
							安途生杯·百日无交通违法挑战赛中奖以及....
						</view>
						<view class="post-info">
							<text class="info-tag1">#热点#</text>
							<text class="info-tag2">7483人浏览</text>
						</view>
					</view>
				</view>
			</view>
			<view class="card-item">
				<view class="card_head">
					<view class="card-head_title">推荐活动</view>
					<view class="card-head_link">查看更多<i class="fa fa-angle-right"></i></view>
				</view>
				<view class="hd-widget">
					<view class="hd-widget_img">
						<image src="../../static/huodong_1.png"></image>
					</view>
					<view class="hd-widget_info">
						<view class="hd_title">
							手头紧张？借钱难？平安银行放款，0抵押，0手续费，快到1小时方款！
						</view>
						<view class="hd_describe">
							平安银行放款，0抵押，0手续费，快到1小时方款！
						</view>
						<view class="hd_meta">
							倒计时
							<view class="meta_time">
								<text>{{tiemObj.day}}</text>天<text>{{tiemObj.hour}}</text>时<text>{{tiemObj.branch}}</text>分<text>{{tiemObj.second}}</text>秒
							</view>
						</view>
						<view class="hd_tags">
							<view class="hd_tag1">#预约报名#</view>
							<view class="hd_tag2">已有3人参加</view>
						</view>
					</view>
				</view>
				<view class="scroll_h">
					<scroll-view scroll-x="true">
						<view class="scroll_h-item" v-for="(item, index) in item_list3" :key="index">
							<image :src="item.imgsrc"></image>
							<text>{{item.text}}</text>
						</view>
					</scroll-view>
				</view>
			</view>
			<view class="card-item">
				<view class="card_head">
					<view class="card-head_title">论吧广场</view>
					<view class="card-head_link">更多<i class="fa fa-angle-right"></i></view>
				</view>
				<view class="hd-widget">
					<view class="hd-widget_img">
						<image src="../../static/huodong_2.jpg"></image>
					</view>
					<view class="hd-widget_info">
						<view class="hd_title">
							你为什么要买奥迪车?
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
				item_list1: [
					{
						text: '养车宝',
						className: 'fa-car pink'
					},
					{
						text: '违章定规',
						className: 'fa-video-camera blue'
					},
					{
						text: '专家问答',
						className: 'fa-commenting-o yellow'
					},
					{
						text: '二手车',
						className: 'fa-car orange'
					},
					{
						text: '福利社',
						className: 'fa-gamepad golden'
					}
				],
				item_list2: [
					'../../static/list-item2_1.png',
					'../../static/list-item2_2.png',
					'../../static/list-item2_3.png'
				],
				item_list3: [
					{
						imgsrc: '../../static/horizontal_1.jpg',
						text: '车购团险'
					},
					{
						imgsrc: '../../static/horizontal_2.jpg',
						text: '我爱自驾游'
					},
					{
						imgsrc: '../../static/horizontal_3.jpg',
						text: '预约过户'
					},
					{
						imgsrc: '../../static/horizontal_4.jpg',
						text: '学生团购报名'
					},
					{
						imgsrc: '../../static/horizontal_5.jpg',
						text: '品牌车友群管家招募'
					},
					{
						imgsrc: '../../static/horizontal_6.jpg',
						text: '抢全车贴膜'
					}
				],
				tiemObj: {
						day: 0,
						hour: 0,
						branch: 0,
						second: 0
				}
			}
		},
		created() {
			this.setScrollViewHeight()
			this.countDown()
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
			},
			iconClass(oldName) {
				return 'fa ' + oldName
			},
			// 倒计时
			countDown() {
				setInterval(() => {
					let closingDate = new Date('2020-11-01')
					let PresentDate = new Date()
					let timeDifference = closingDate - PresentDate
					let day = Math.floor(timeDifference/(1000*60*60*24))
					timeDifference %= (1000*60*60*24)
					let hour = Math.floor(timeDifference/(1000*60*60))
					timeDifference %= (1000*60*60)
					let branch = Math.floor(timeDifference/(1000*60))
					timeDifference %= (1000*60)
					let second = Math.floor(timeDifference/1000)
					this.tiemObj = {
						day,
						hour,
						branch,
						second
					}
				}, 1000)
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		background-color: #eee;
	}
	.card-item {
		/* height: 400rpx; */
		width: 100%;
		background-color: #FFFFFF;
		margin-bottom: 10rpx;
		padding-bottom: 40rpx;
	}
	.card-item .branner image {
		width: 100%;
		height: 300rpx;
	}
	.card-item .row-list1 {
		height: 200rpx;
		display: flex;
		flex-direction: row;
	}
	.row-list1 .list-item {
		width: 25%;
		text-align: center;
	}
	.row-list1 .list-item i {
		display: block;
		line-height: 80rpx;
		width: 80rpx;
		height: 80rpx;
		margin: 20rpx auto;
		font-size: 50rpx;
		color: #FFFFFF;
		border-radius: 50%;
	}
	.row-list1 .list-item text {
		font-size: 20rpx;
	}
	.pink {
		background-color: #ff058a;
	}
	.blue {
		background-color: #02c4ff;
	}
	.yellow {
		background-color: #ff5500;
	}
	.orange {
		background-color: #ffaa00;
	}
	.golden {
		background-color: #ffff00;
	}
	.row-list2 {
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		height: 220rpx;
	}
	.row-list2 .list-item {
		width: 30%;
		height: 200rpx;
	}
	.row-list2 .list-item image {
		border-radius: 20rpx;
		width: 100%;
		height: 100%;
	}
	.row-posts .item-post {
		width: 100%;
		margin-top: 40rpx;
		padding: 0 30rpx;
	}
	.row-posts .post-title {
		font-weight: bold;
		border-left: 10rpx solid #f1f100;
		padding-left: 20rpx;
	}
	.row-posts .post-info {
		font-size: 24rpx;
		padding-top: 10rpx;
		padding-left: 30rpx;
	}
	.post-info .info-tag1 {
		color: #ff0000;
	}
	.post-info .info-tag2 {
		color: #ccc;
		margin-left: 50rpx;
	}
	.card_head {
		box-sizing: border-box;
		width: 100%;
		height: 90rpx;
		line-height: 90rpx;
		padding: 0rpx 30rpx;
	}
	.card_head .card-head_title {
		height: 100%;
		float: left;
	}
	.card_head .card-head_link {
		height: 100%;
		color: #C0C0C0;
		font-size: 25rpx;
		float: right;
	}
	.card_head .card-head_link i {
		display: inline-block;
		margin-left: 10rpx;
	}
	.card-item .hd-widget {
		margin: 0 30rpx;
		box-shadow: 0 0 20rpx #C0C0C0;
	}
	.hd-widget .hd-widget_img {
		height: 300rpx;
		width: 100%;
	}
	.hd-widget .hd-widget_img image {
		width: 100%;
		height: 100%;
	}
	.hd-widget .hd-widget_info {
		padding: 0 20rpx;
	}
	.hd-widget_info .hd_title {
		font-weight: bold;
		font-size: 40rpx;
		padding: 20rpx 0;
	}
	.hd-widget_info .hd_describe {
		font-size: 20rpx;
		color: #CCCCCC;
	}
	.hd-widget_info .hd_meta {
		height: 90rpx;
		line-height: 90rpx;
		width: 100%;
		font-size: 30rpx;
		padding-bottom: 20rpx;
		border-bottom: 2rpx solid #CCCCCC;
	}
	.hd_meta .meta_time {
		float: right;
		font-size: 25rpx;
		padding: 15rpx 0;
	}
	.hd_meta .meta_time text {
		display: inline-block;
		border: 1rpx solid #333;
		width: 60rpx;
		height: 60rpx;
		line-height: 60rpx;
		text-align: center;
		font-size: 40rpx;
		margin: 0 10rpx;
	}
	.hd-widget .hd_tags {
		height: 80rpx;
		line-height: 80rpx;
		font-size: 20rpx;
	}
	.hd_tags .hd_tag1 {
		float: left;
		color: #f1f100;
	}
	.hd_tags .hd_tag2 {
		float: right;
		color: #C0C0C0;
	}
	.scroll_h {
		width: 100%;
		height: 240rpx;
		padding-top: 30rpx;
	}
	.scroll_h scroll-view {
		width: 100%;
		height: 100%;
		white-space: nowrap;
	}
	.scroll_h .scroll_h-item {
		width: 30%;
		height: 200rpx;
		display: inline-block;
		margin: 20rpx 30rpx;
		box-shadow: 0 0 10rpx #CCCCCC;
	}
	.scroll_h-item image {
		width: 100%;
		height: 160rpx;
	}
	.scroll_h-item text {
		display: block;
		height: 40rpx;
		line-height: 1;
		text-align: center;
		font-size: 30rpx;
		overflow: hidden;
		text-overflow: ellipsis;
	}
	.card-item:last-child {
		margin-bottom: 0;
	}
	.nav-title {
		height: 88rpx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
	.nav-title image {
		display: block;
		width: 88rpx;
		height: 88rpx;
	}
	.nav-title text {
		display: block;
	}
</style>
