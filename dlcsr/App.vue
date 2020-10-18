<script>
	import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue"
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		},
		components: {
			uniNavBar
		}
	}
</script>

<style>
	/*每个页面公共css */
	/* 自定义导航栏 */
	.nav-title {
		width: 100%;
		text-align: center;
		font-weight: 900;
	}
	.nav-left {
		width: 100%;
		text-align: center;
		font-size: 30rpx;
	}
	.nav-left i {
		font-size: 40rpx;
		display: inline-block;
		margin-left: 10rpx;
	}
	.nav-right {
		width: 100%;
		text-align: center;
	}
	.nav-right i {
		display: inline-block;
		margin: 0 5px;
		font-size: 40rpx;
	}
	.nav-right i:hover {
		color: #F1F100;
	}
	/* #ifdef H5 */ 
	uni-scroll-view .uni-scroll-view::-webkit-scrollbar { 
		/* 隐藏滚动条，但依旧具备可以滚动的功能 */ 
		display: none
	}
	/* #endif */
</style>
