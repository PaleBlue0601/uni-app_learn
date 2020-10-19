<template>
	<view>
		<scroll-view scroll-y="true" class="content-scroll">
			<view class="main">
				<!-- 文章 -->
				<view class="post-widget">
					<view class="post-head_img">
						<image :src="posts[index].imgurl1" mode=""></image>
					</view>
					<view class="post-info">
						<view class="post-info_title">
							{{posts[index].title}}
						</view>
						<view class="post-info_content">
							<text>
								{{posts[index].content}}
							</text>
						</view>
						<view class="post-info_tag">
							#老司机#
						</view>
					</view>
				</view>
				<view class="post-hd">
					<view class="post-hd_head">
						<text class="head-left">大连车事儿app</text>
						<text class="head-right">{{posts[index].tiem}}</text>
					</view>
					<view class="post-hd_img">
						<image :src="posts[index].imgurl2"></image>
					</view>
				</view>
				<!-- 评论 -->
				<view class="post-column">
					<view class="b-head">
						<i class="fa fa-eye" aria-hidden="true"></i>
						<text>话题评论</text>
						<text class="b-head-count">({{posts[index].count}}条)</text>
					</view>
					<view class="c-head">
						<view :class="navClass1" @click="toggleColumn(true)">最热</view>
						<view :class="navClass2" @click="toggleColumn(false)">最新</view>
					</view>
					<view class="c-list">
						<view class="c-item" v-for="(item, index) in posts[index].commentData" :key="index">
							<view class="item-head">
								<view class="meta-portrait">
									<image :src="item.tx_url"></image>
								</view>
								<view class="head-metas">
									<view class="meta_name">{{item.name}}</view>
									<view class="meta_time">{{item.tiem}}</view>
								</view>
							</view>
							<view class="meta-content">
								{{item.content}}
							</view>
							<view class="meta-tags">
								<view class="tag-dis">
									<i class="fa fa-commenting-o" aria-hidden="true"></i>
									<text>评论</text>
								</view>
								<view class="tag-up">
									<i class="fa fa-thumbs-up" aria-hidden="true"></i>
									<text>点赞</text>
								</view>
								<view class="tag-report">
									<text>举报</text>
								</view>
							</view>
						</view>
					</view>
				</view>
				<!-- 发表评论 -->
				<view class="column-send">
					<view class="meta-back" @click="toBack">
						<i class="fa fa-chevron-left" aria-hidden="true"></i>
					</view>
					<view class="meta-input">
						<input type="text" placeholder="请发布您的的图片或评论..." />
					</view>
					<view class="like_share">
						<view class="like" @click="like">
							<i class="fa fa-heart-o" aria-hidden="true" ref="like"></i><text>{{like_count}}</text>
						</view>
						<view class="share">
							<i class="fa fa-share-square-o" aria-hidden="true"></i><text>8</text>
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
				index: 0,
				posts: [
					{
						imgurl1: '../../static/post/post_1-1.jpg',
						imgurl2: '../../static/post/post_1-2.jpg',
						title: '你为什么要买奥迪车？',
						content: `你为什么买奥迪车?
						多少钱买？
						开上之后有什么不满意的地方吗？
						参与评论有车贝奖励哦~`,
						tiem: '2天前',
						count: 8,
						commentData: [
							{
								tx_url: '../../static/post/tx_man.png',
								name: '火霹雳',
								tiem: '7小时前',
								content: '不会买奥迪车，应为我买不起啊！'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '车小粉',
								tiem: '8小时前',
								content: '零件国产化程度较高'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '小鱼儿',
								tiem: '10小时前',
								content: '不会买奥迪车，应为我买不起啊！'
							},
							{
								tx_url: '../../static/post/tx_man.png',
								name: '李四',
								tiem: '18小时前',
								content: '装门面'
							}
						]
					},
					{
						imgurl1: '../../static/post/post_2-1.jpg',
						imgurl2: '../../static/post/post_2-2.jpg',
						title: '七夕活动:执子之手，以子偕老晒步数赢好礼',
						content: '活动奖品：大连车事儿三件套1套：车主专用反向伞，抱枕，草莓袋',
						tiem: '2天前',
						count: 116,
						commentData: [
							{
								tx_url: '../../static/post/tx_man.png',
								name: '用户1',
								tiem: '2小时前',
								content: '搞活动'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '用户2',
								tiem: '7小时前',
								content: '不错'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '小鱼儿',
								tiem: '10小时前',
								content: '这个活动没赶上'
							},
							{
								tx_url: '../../static/post/tx_man.png',
								name: '李四',
								tiem: '18小时前',
								content: '愿天有情人终成眷属！'
							}
						]
					},
					{
						imgurl1: '../../static/post/post_3-1.jpg',
						imgurl2: '../../static/post/post_3-2.jpg',
						title: '一盔一带:安全带打卡',
						content: '各位车友，截止6月17日本次安全带打卡活动以已经截止统计，现将在活动期间打卡满10天及以上的车友中抽取活动大奖',
						tiem: '05-25',
						count: 5228,
						commentData: [
							{
								tx_url: '../../static/post/tx_man.png',
								name: '用户1',
								tiem: '2小时前',
								content: '打卡'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '用户2',
								tiem: '7小时前',
								content: '不错'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '小鱼儿',
								tiem: '10小时前',
								content: '这个活动没赶上'
							},
							{
								tx_url: '../../static/post/tx_man.png',
								name: '李四',
								tiem: '18小时前',
								content: '打卡'
							}
						]
					},
					{
						imgurl1: '../../static/post/post_4-1.jpg',
						imgurl2: '../../static/post/post_4-2.jpg',
						title: '有人跟你借车你会借吗?',
						content: `借车给朋友出事还要车主赔偿？
						有人跟你借车，你会借吗？
						都来说说...`,
						tiem: '05-13',
						count: 5228,
						commentData: [
							{
								tx_url: '../../static/post/tx_man.png',
								name: '用户1',
								tiem: '2小时前',
								content: '打卡'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '用户2',
								tiem: '7小时前',
								content: '不错'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '小鱼儿',
								tiem: '10小时前',
								content: '这个活动没赶上'
							},
							{
								tx_url: '../../static/post/tx_man.png',
								name: '李四',
								tiem: '18小时前',
								content: '打卡'
							}
						]
					},
					{
						imgurl1: '../../static/post/post_5-1.jpg',
						imgurl2: '../../static/post/post_5-2.jpg',
						title: '老婆开车你敢做副驾驶吗?',
						content: `老婆开车你敢做副驾驶吗?
						快来说说你的经历...`,
						tiem: '05-25',
						count: 221,
						commentData: [
							{
								tx_url: '../../static/post/tx_man.png',
								name: '用户1',
								tiem: '2小时前',
								content: '打卡'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '用户2',
								tiem: '7小时前',
								content: '不错'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '小鱼儿',
								tiem: '10小时前',
								content: '这个活动没赶上'
							},
							{
								tx_url: '../../static/post/tx_man.png',
								name: '李四',
								tiem: '18小时前',
								content: '打卡'
							}
						]
					},
					{
						imgurl1: '../../static/post/post_6-1.jpg',
						imgurl2: '../../static/post/post_6-2.jpg',
						title: '这个五一很特别你在干啥?',
						content: `这个五一很特别。你在干啥？
						你有什么计划吗？`,
						tiem: '05-25',
						count: 53,
						commentData: [
							{
								tx_url: '../../static/post/tx_man.png',
								name: '用户1',
								tiem: '2小时前',
								content: '打卡'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '用户2',
								tiem: '7小时前',
								content: '不错'
							},
							{
								tx_url: '../../static/post/tx_girl.png',
								name: '小鱼儿',
								tiem: '10小时前',
								content: '这个活动没赶上'
							},
							{
								tx_url: '../../static/post/tx_man.png',
								name: '李四',
								tiem: '18小时前',
								content: '打卡'
							}
						]
					},
				],
				navClass1: {
					nav: true,
					active: true
				},
				navClass2: {
					nav: true,
					active: false
				},
				like_count: 0
			}
		},
		onLoad(option) {
			this.index = parseInt(option.index)
			// console.log(this.index)
		},
		methods: {
			toBack() { //返回上一页
				uni.navigateBack({
					delta: 1
				})
			},
			toggleColumn(check) { //切换评论
				if(check) {
					if(this.navClass1.active != true){
						this.navClass1.active = true
						this.navClass2.active = false
						this.posts[this.index].commentData.reverse()
					}
				} else {
					if(this.navClass2.active != true){
						this.navClass1.active = false
						this.navClass2.active = true
						this.posts[this.index].commentData.reverse()
					}
				}
			},
			like() {
				if(this.like_count == 0) {
					this.$refs.like.style.color = 'red'
					this.like_count = 1
				} else {
					this.$refs.like.style.color = 'black'
					this.like_count = 0
				}
			}
		}
	}
</script>

<style>
	.content-scroll {
		height: 100%;
		width: 100%;
		position: absolute;
		top: 0px;
		bottom: 0px;
	}
	.main {
		display: flex;
		flex-direction: column;
		justify-content: center;
		flex-wrap: wrap;
		position: relative;
	}
	 .post-widget .post-head_img image{
		width: 100%;
		height: 500rpx;
	}
	.post-widget .post-info {
		padding: 30rpx;
		box-sizing: border-box;
	}
	.post-info .post-info_title {
		font-weight: bold;
		font-size: 50rpx;
	}
	.post-info .post-info_content {
		color: #CCCCCC;
		font-size: 30rpx;
		line-height: 1.5;
		padding-bottom: 30rpx;
		border-bottom: 2rpx solid #CCCCCC;
	}
	.post-info .post-info_tag {
		padding: 20rpx 0;
		color: #eaea00;
		font-size: 28rpx;
	}
	.post-hd {
		border-bottom: 15rpx solid #EEEEEE;
	}
	.post-hd_head {
		box-sizing: border-box;
		font-size: 20rpx;
		padding: 0 30rpx 20rpx 30rpx;
		width: 100%;
	}
	.post-hd_head .head-right {
		float: right;
	}
	.post-hd .post-hd_img {
		height: 240rpx;
	}
	.post-hd .post-hd_img image {
		width: 100%;
		height: 100%;
	}
	.post-column {
		padding: 0 30rpx;
		margin-bottom: 78rpx;
	}
	.b-head {
		box-sizing: border-box;
		padding: 20rpx 0;
	}
	.b-head .fa-eye {
		display: inline-block;
		font-size: 40rpx;
		margin-right: 20rpx;
	}
	.b-head .b-head-count {
		display: inline-block;
		margin-left: 20rpx;
		color: #CCCCCC;
	}
	.c-head {
		height: 56rpx;
		border-bottom: 2rpx solid #EEEEEE;
	}
	.c-head .nav {
		display: inline-block;
		margin-right: 40rpx;
		height: 56rpx;
		line-height: 56rpx;
	}
	.active {
		border-bottom: 4rpx solid #eaea00;
	}
	.c-list .item-head {
		height: 80rpx;
		margin: 10rpx 0;
	}
	.item-head .meta-portrait {
		display: inline-block;
		width: 80rpx;
		height: 80rpx;
		border-radius: 50%;
	}
	.item-head .meta-portrait image {
		width: 100%;
		height: 100%;
	}
	.item-head .head-metas {
		display: inline-block;
		height: 80rpx;
		margin-left: 20rpx;
	}
	.head-metas .meta_time {
		color: #CCCCCC;
		font-size: 10rpx;
	}
	.c-list .c-item {
		border-bottom: 6rpx solid #EEEEEE;
	}
	.c-item .meta-content {
		font-size: 26rpx;
		margin: 20rpx 0;
	}
	.c-item .meta-tags {
		height: 60rpx;
		font-size: 20rpx;
	}
	.meta-tags view {
		display: inline-block;
	}
	.meta-tags .tag-dis {
		margin-right: 20rpx;
	}
	.meta-tags i {
		margin-right: 10rpx;
	}
	.meta-tags .tag-report {
		color: #007AFF;
		float: right;
	}
	.column-send {
		width: 100%;
		height: 80rpx;
		position: fixed;
		background-color: #FFFFFF;
		border-top: 1rpx solid #CCCCCC;
		bottom: 0;
		display: flex;
		flex-direction: row;
	}
	.column-send .meta-back {
		width: 15%;
		line-height: 80rpx;
		text-align: center;
		font-size: 40rpx;
	}
	.column-send .meta-input {
		width: 55%;
		height: 60rpx;
		background-color: #EEEEEE;
		border-radius: 10rpx;
		margin: 10rpx 0;
	}
	.column-send .meta-input input {
		box-sizing: border-box;
		height: 60rpx;
		font-size: 26rpx;
		padding-left: 20rpx;
	}
	.column-send .like_share {
		width: 30%;
		line-height: 80rpx;
		font-size: 40rpx;
	}
	.column-send .like_share * {
		display: inline-block;
	}
	.like_share .like {
		margin-left: 20rpx;
	}
	.like_share .like text,
	.like_share .share text{
		margin-left: 10rpx;
	}
	.like_share .share {
		float: right;
		margin-right: 20rpx
	}
</style>
