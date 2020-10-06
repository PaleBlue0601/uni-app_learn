<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	* {
		box-sizing: border-box;
	}
	.flex {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		align-items: center;
	}
	.flex-item {
		text-align: center;
		margin: 20px auto;
		font-size: 30rpx;
		color: #C0C0C0;
		width: 100%;
		padding: 15rpx;
	}
	.flex .title {
		color: #bebebe;
		padding: 0 20px;
		font-size: 30rpx;
		height: 80rpx;
		line-height: 80rpx;
		border-bottom: 1px solid #d8d8d8;
	}
</style>
