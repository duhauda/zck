<template>
	<view>
		<view>

			<view class="info-box">
				<view class="info-heart">
					<image class="avatar" style="height: 120rpx;width: 120rpx;border-radius: 100%;"
						src="../../static/logo.png" mode="">
					</image>
					<view class="user-name">
						xxx
					</view>
					<image class="info-side" style="height: 30rpx;width: 30rpx;border-radius: 100%;"
						src="../../static/images/women.png">
					</image>
				</view>
			</view>

			<view class="more-box">
				<view class="item">
					<view class="left-box">
						<image src="@/static/images/locations.png" style="height: 35rpx;width: 35rpx;" mode=""></image>
						<view class="item-name">
							地址管理
						</view>
					</view>
					<u-icon name="arrow-right"></u-icon>
				</view>

				<view class="item">
					<view class="left-box">
						<image src="@/static/images/orders.png" style="height: 35rpx;width: 35rpx;" mode=""></image>
						<view class="item-name">
							历史订单
						</view>
					</view>
					<u-icon name="arrow-right"></u-icon>
				</view>

			</view>

			<view class="">
				退出登录
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss">
	page {
		background: #f8f8f8;
	}

	.info-box {
		background-color: #ffc200;

		.info-heart {
			width: 90%;
			margin: 0 auto;
			display: flex;
			align-items: center;
			padding: 20rpx 0;

			.avatar {
				margin-right: 30rpx;
			}

			.user-name {
				margin-right: 10rpx;
			}

			.info-side {
				padding: 10rpx 0 0 0;
			}
		}
	}

	.more-box {
		margin: 0 auto;
		width: 90%;
		background: white;
		border-radius: 20rpx;

		.item {
			padding: 20rpx;
			display: flex;
			align-items: center;
			justify-content: space-between;

			.left-box {
				display: flex;
				align-items: center;

				.item-name {
					margin-left: 10rpx;
					font-size: 20rpx;
				}
			}
		}
	}
</style>