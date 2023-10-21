<template>
	<view class="login-other">
		<view class="other-text">
		<view>或用以下方式登录</view>
		</view>
		<view class="other">
			<view class="other-item">
				<img src="../../static/images/微信.png" alt="">
				<view>微信登录</view>	
			</view>
			
			<view class="other-item">
				<img src="../../static/images/QQ.png" alt="">
				<view>QQ登录</view>	
			</view>
			<view class="other-item">
				<img src="../../static/images/支付宝.png" alt="">
				<view>支付宝登录</view>	
			</view>
		</view>
	</view>
</template>

<script>
</script>

<style lang="scss">
	
	/*其他登录*/
	.login-other{
		padding: 20rpx 0;
	}
	.other-text{
		display: flex;
		padding: 50rpx 0;
	}
	.other-text view{
		line-height: 0rpx;
		padding: 0 10rpx;
	}
	.other-text::after{
		flex: 1;
		content: '';
		height: 2rpx;
		background-color: #CCCCCC;
	}
	.other-text::before{
		flex: 1;
		content: '';
		height: 2rpx;
		background-color: #CCCCCC;
	}
	.other{
		display: flex;
		justify-content: space-around;
	}
	.other-item{
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.other-item img{
		width: 80rpx;
		height: 80rpx;
	}
	/*其他登录 end*/
</style>