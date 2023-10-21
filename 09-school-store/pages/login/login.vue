<template>
	<view>
		<view class="logo-box">
			<image src="../../static/images/Ninelogo.png" mode=""></image>
			<view class="logo-font">星原校园</view>
		</view>
		<view class="form-box">

			<u--input @input='check' placeholder="请输入账号" :clearable='true' customStyle='background-color: white;
						width: 75%;
						margin: auto;
						border: solid 1rpx #999;
						margin-top: 40rpx;
						padding: 20rpx 30rpx;
						border-radius: 20rpx;' v-model="loginAccount">
			</u--input>
			<u--input @input='check' placeholder="请输入密码" :clearable='true' customStyle='background-color: white;
						width: 75%;
						margin: auto;
						border: solid 1rpx #999;
						margin-top: 40rpx;
						padding: 20rpx 30rpx;
						border-radius: 20rpx;' :password='true' v-model="loginPassword">
			</u--input>


			<u-button class="login-btn" text="登录" shape="circle" :color="color" @click="login"></u-button>
		</view>
		<view class="check-box">
			<u-radio-group>
				<u-radio>勾选即表示同意<text style="color:coral ;">《用户协议》</text>及<text style="color:coral ;">《隐私政策》</text>
				</u-radio>
			</u-radio-group>
		</view>
		<view class="register">
			没有账号?<text @click="toRegister" style="color: coral;">前往注册</text>
		</view>
		<LoginOther></LoginOther>


	</view>
</template>

<script>
	import LoginOther from '@/components/login/login-other.vue'
	export default {
		data() {
			return {



				loginAccount: '',
				loginPassword: '',
				color: '#c7c0d1'
			};
		},
		components: {
			LoginOther
		},
		methods: {

			login() {
				if (this.color == '#c7c0d1') {
					uni.showToast({
						title: '请输用户名与密码',
						icon: 'none'
					})
				} else {
					console.log(this.loginAccount, this.loginPassword);
					uni.showToast({
						title: '登录成功',
						icon: 'none'
					})

				}
			},
			check() {
				if (this.loginAccount.length > 0 && this.loginPassword.length > 0) {
					this.color = '#ad8dd1'
				} else {
					this.color = '#c7c0d1'
				}
			},
			toRegister() {
				uni.navigateTo({
					url: '/pages/register/register'
				})
			}
		}
	}
</script>

<style lang="scss">
	page {
		background: linear-gradient(148deg, #FFFFFF -31%, #fffbb8 14%, #fff4b3 27%, #fff5b4 200%);

	}

	.logo-box {
		padding: 60rpx 0;
		text-align: center;

		image {
			height: 160rpx;
			width: 160rpx;
			border-radius: 100%;
		}
	}

	.logo-font {
		font-size: 46rpx;
		color: #FFB6C1;
		font-weight: bold;
	}

	.form-box {
		width: 90vw;
		margin: 0 auto;


		.login-btn {
			display: flex;
			align-items: center;
			justify-content: center;
			margin: 62rpx auto 0;
			width: 120rpx;
			height: 120rpx;
			border-radius: 50%;
			background-color: #000;
		}
	}

	.check-box {
		display: flex;
		padding: 20rpx 0;
		margin-left: 30rpx;
	}

	.register {
		color: #b9acd1;
		margin: 0 30vw;
		padding-top: 20rpx;

	}
</style>