<template>
	<view class="column">
		<uni-nav-bar>
			<view class="nav-title">栏目</view>
			<view class="nav-right" slot="right">
				<i class="fa fa-bell-o" aria-hidden="true"></i>
			</view>
		</uni-nav-bar>
		<scroll-view scroll-y="true" class="column-scroll">
			<view class="content">
				<view class="search-widget">
					<input class="search-widget_input" type="text" :value="inputvalue" @blur="addTimer" @focus="delTimer"/>
					<i class="fa fa-search" aria-hidden="true"></i>
				</view>
				<view class="category-widget">
					<view class="category-item" v-for="(item, index) in category" :key="index">
						<image :src="item.imgsrc" ></image>
						<text>{{item.text}}</text>
					</view>
				</view>
				<view class="select-widget">
					<view class="select-widget_bg">
						<view class="img_cover" v-show="!isShowBrannerName">
							<i class="fa fa-plus" aria-hidden="true" @click="showList"></i>
							<text>选择您的车型\n</text>
							<text>为您匹配服务以及产品</text>
						</view>
						<view class="img_cover" v-show="isShowBrannerName">
							<view class="branner-text">
								{{selectBranner}}
							</view>
						</view>
					</view>
				</view>
				<!-- 品牌列表 -->
				<view class="brand-list" v-show="isShowList">
					<view class="brand-item" v-for="(item, index) in brands" :key="index" @click="selectCar(index)">
						<text>{{item}}</text>
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
				category: [
					{
						imgsrc: '../../static/column/洗车服务.png',
						text: '去洗车'
					},
					{
						imgsrc: '../../static/column/汽车保养.png',
						text: '做保养'
					},
					{
						imgsrc: '../../static/column/汽车装饰.png',
						text: '美容贴膜'
					},
					{
						imgsrc: '../../static/column/清洗.png',
						text: '清洗养护'
					},
					{
						imgsrc: '../../static/column/汽车维修.png',
						text: '改装调优'
					},
					{
						imgsrc: '../../static/column/喷漆.png',
						text: '钣金喷漆'
					},
					{
						imgsrc: '../../static/column/维修.png',
						text: '维修换件'
					},
					{
						imgsrc: '../../static/column/商城.png',
						text: '商城'
					}
				],
				inputvalue: '米狗',
				timer: '',
				brands: ['奥迪','宝马','大众','奔驰','宾利','丰田','本田','路虎','悍马'],
				selectBranner: '奥迪',
				isShowBrannerName: false,
				isShowList: false
			}
		},
		created() {
			this.switchInputvalue()
		},
		methods: {
			// 使用定时器实现inputvalue值的定时切换
			switchInputvalue() {
				let arrValue = ['挡风玻璃防雾剂','方向盘套','机油','嘉实多','米狗']
				let index = 0
				this.timer = setInterval(() => {
					this.inputvalue = arrValue[index]
					index = ++index % arrValue.length
					// console.log(this.inputvalue)
				}, 3000)
			},
			// 删除定时器
			delTimer() {
				clearInterval(this.timer)
			},
			// 重新添加定时器
			addTimer() {
				this.switchInputvalue()
			},
			showList() { //显示品牌列表
				this.isShowList = true
			},
			selectCar(index) {
				this.selectBranner = this.brands[index]
				this.isShowList = false
				this.isShowBrannerName = true
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
	.search-widget {
		width: 100%;
		box-sizing: border-box;
		padding: 20rpx 30rpx;
		background-color: #FFFFFF;
		position: relative;
	}
	.search-widget .search-widget_input {
		width: 100%;
		box-sizing: border-box;
		border-radius: 40rpx;
		padding-left: 80rpx;
		height: 60rpx;
		line-height: 60rpx;
		background-color: #EEEEEE;
	}
	.search-widget .fa-search {
		position: absolute;
		display: block;
		top: 32rpx;
		left: 56rpx;
	}
	.category-widget {
		width: 100%;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		background-color: #FFFFFF;
		border-bottom: 4rpx solid #EEEEEE;
	}
	.category-item {
		display: inline-block;
		box-sizing: border-box;
		width: 25%;
		height: 230rpx;
		padding: 20rpx 20rpx;
		text-align: center;
	}
	.category-item image {
		display: block;
		margin: 0 auto;
		width: 120rpx;
		height: 120rpx;
	}
	.category-item text {
		display: block;
		height: 70rpx;
		line-height: 70rpx;
		font-size: 28rpx;
	}
	.select-widget {
		width: 100%;
		box-sizing: border-box;
		padding:0 30rpx;
		background-color: #FFFFFF;
		position: relative;
	}
	.select-widget .select-widget_bg {
		width: 100%;
		margin: 40rpx 0;
		height: 240rpx;
		display: grid;
		place-items: center;
		background-image: url(../../static/column/bg.png);
	}
	.select-widget_bg .img_cover {
		width: 480rpx;
		height: 120rpx;
	}
	.img_cover .fa-plus {
		display: block;
		float: left;
		width: 120rpx;
		height: 120rpx;
		border-radius: 50%;
		background-color: #FFFFFF;
		border: 2rpx solid #EEEEEE;
		text-align: center;
		line-height: 120rpx;
		margin-right: 30rpx;
	}
	.img_cover text:last-child {
		display: inline-block;
		margin-top: 10rpx;
		font-size: 28rpx;
	}
	.brand-list {
		width: 100%;
		background-color: #FFFFFF;
		padding: 0 30rpx;
		box-sizing: border-box;
	}
	.brand-list .brand-item {
		box-sizing: border-box;
		padding: 20rpx 30rpx;
		border-bottom: 2rpx solid #CCCCCC;
		text-align: left;
	}
	.column-scroll {
		height: 573px;
	}
	.branner-text {
		text-align: center;
		line-height: 120rpx;
		font-size: 40rpx;
	}
</style>
