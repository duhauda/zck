<template>
	<view class="userCenter">
		<view class="info-box">
			<view class="info-heart">
				<image src="../../static/images/headPage.png" mode="" style="height: 120rpx;
				width: 120rpx; 
				border-radius: 100%; 
				box-shadow: 10rpx 10rpx 10rpx #000;" class="avatar"></image>
				<view class="user-name" style="margin-right: 10rpx;">星原校园</view>
				<!-- <u-icon @click="change" name="man" color="#2979ff" size="16" v-if='flag'></u-icon> -->
				<u-icon name="woman" color="#ca2188" size="16"></u-icon>
				<u-icon name="arrow-right" style="margin-left: 34vw;" @click="toInfo"></u-icon>
				</image>
				<view class="">

				</view>
			</view>
		</view>



		<view class="box">

			<view class="address-box">
				<view class="item">
					<view class="left-box">

						<image src="@/static/images/地址.png" style="height: 35rpx;width: 35rpx;" mode=""></image>

						<view class="item-name">
							地址管理
						</view>
					</view>
					<u-icon name="arrow-right"></u-icon>
				</view>
			</view>





			<view class="more-box">
				<view class="item">
					<view class="left-box">
						<image src="@/static/images/订单.png" style="height: 35rpx;width: 35rpx;" mode=""></image>


						<view class="item-name">
							订单管理
						</view>
					</view>
					<u-icon name="arrow-right"></u-icon>
				</view>

			</view>



			<view class="FavoriteShops-box">
				<view class="item">
					<view class="left-box">

						<image src="@/static/images/商家.png" style="height: 35rpx;width: 35rpx;" mode=""></image>

						<view class="item-name">
							收藏商家
						</view>
					</view>
					<u-icon name="arrow-right"></u-icon>
				</view>
			</view>

			<view class="card-box">
				<view class="item">
					<view class="left-box">
						<image src="@/static/images/优惠券.png" style="height: 35rpx;width: 35rpx;" mode=""></image>


						<view class="item-name">
							红包卡卷
						</view>
					</view>
					<u-icon name="arrow-right"></u-icon>
				</view>

			</view>



			<view class="BrowsingHistory-box">
				<view class="item">
					<view class="left-box">

						<image src="@/static/images/历史记录.png" style="height: 35rpx;width: 35rpx;" mode=""></image>

						<view class="item-name">
							浏览历史
						</view>
					</view>
					<u-icon name="arrow-right"></u-icon>
				</view>
			</view>


			<view class="Personal-settings">
				<view class="item">
					<view class="left-box">
						<image src="@/static/images/设置.png" style="height: 35rpx;width: 35rpx;" mode=""></image>


						<view class="item-name">
							个人设置
						</view>
					</view>
					<u-icon name="arrow-right"></u-icon>
				</view>

			</view>

		</view>
		<!-- <view class="">
			退出登录
		</view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				img: [
					'../../static/images/性别女.png',
					'../../static/images/性别-男.png'
				],
				gender: 0,
				flag: true
			};
		},

		methods: {
			change() {
				this.flag = !this.flag
			},
			toInfo() {
				uni.navigateTo({
					url: '/pages/info/info'
				})
			}
		}
	}
</script>

<style lang="scss">
	page {
		background: linear-gradient(148deg, #FFFFFF -31%, #fffbb8 14%, #fff4b3 27%, #fff5b4 200%);
	}



	.userCenter {
		padding: 30rpx 30rpx;
		border-radius: 100%;

		height: 100vh; //消除横线
	}

	.info-box {
		background-color: #fff4b3;
		border-radius: 25px;
		border: 2px solid #FFB6C1;

		.info-heart {
			display: flex;
			align-items: center;
			width: 90%;
			margin: 0 auto;
			padding: 20rpx 0;


			.user-name {
				// margin-right: 10rpx;
				font-weight: bold;
			}

			.avatar {
				margin-right: 30rpx;
			}
		}

	}

	.box {
		padding: 20rpx 0;
	}

	.address-box {
		justify-content: center;
		width: 90%;
		margin: 20rpx;
		position: relative;
		background: white;
		border-radius: 20rpx;

		.item {
			display: flex;
			align-items: center;
			justify-content: space-between;
			padding: 30rpx;

		}

		.left-box {
			display: flex;
			align-items: center;

		}

		.item-name {
			margin-left: 10rpx;
			font-size: 20rpx;
		}
	}

	.more-box {
		justify-content: center;
		position: relative;
		width: 90%;
		margin: 20rpx;
		background: white;
		border-radius: 20rpx;

		.item {
			display: flex;
			align-items: center;
			justify-content: space-between;
			padding: 30rpx;

		}

		.left-box {
			display: flex;
			align-items: center;

		}

		.item-name {
			margin-left: 10rpx;
			font-size: 20rpx;
		}
	}



	.FavoriteShops-box {
		justify-content: center;
		width: 90%;
		margin: 20rpx;
		position: relative;
		background: white;
		border-radius: 20rpx;

		.item {
			display: flex;
			align-items: center;
			justify-content: space-between;
			padding: 30rpx;

		}

		.left-box {
			display: flex;
			align-items: center;

		}

		.item-name {
			margin-left: 10rpx;
			font-size: 20rpx;
		}
	}

	.card-box {
		justify-content: center;
		position: relative;
		width: 90%;
		margin: 20rpx;
		background: white;
		border-radius: 20rpx;

		.item {
			display: flex;
			align-items: center;
			justify-content: space-between;
			padding: 30rpx;

		}

		.left-box {
			display: flex;
			align-items: center;

		}

		.item-name {
			margin-left: 10rpx;
			font-size: 20rpx;
		}
	}

	.BrowsingHistory-box {
		justify-content: center;
		width: 90%;
		margin: 20rpx;
		position: relative;
		background: white;
		border-radius: 20rpx;

		.item {
			display: flex;
			align-items: center;
			justify-content: space-between;
			padding: 30rpx;

		}

		.left-box {
			display: flex;
			align-items: center;

		}

		.item-name {
			margin-left: 10rpx;
			font-size: 20rpx;
		}
	}

	.Personal-settings {
		justify-content: center;
		width: 90%;
		margin: 20rpx;
		position: relative;
		background: white;
		border-radius: 20rpx;

		.item {
			display: flex;
			align-items: center;
			justify-content: space-between;
			padding: 30rpx;

		}

		.left-box {
			display: flex;
			align-items: center;

		}

		.item-name {
			margin-left: 10rpx;
			font-size: 20rpx;
		}
	}
</style>