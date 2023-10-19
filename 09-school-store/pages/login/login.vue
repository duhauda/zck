<template>
	<view>
		<view class="logo-box">
			<image style="height: 160rpx;width: 160rpx;" src="../../static/logo.png" mode=""></image>
			<view class="">校店</view>
		</view>
		<view class="form-box">
			<u--input @input='check' placeholder="请输入账号" :clearable='true' customStyle='background-color: white;'
				v-model="loginAccount"></u--input>
			<u--input @input='check' placeholder="请输入密码" :clearable='true'
				customStyle='background-color: white;margin-top: 10rpx;' :password='true'
				v-model="loginPassword"></u--input>
			<u-button class="login-btn" text="登录" shape="circle" :color="color" @click="login"></u-button>
		</view>
		<view class="register" @click="toRegister">
			没有账号?前往注册
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				loginAccount: '',
				loginPassword: '',
				color: '#d8d8d8'
			};
		},
		methods: {
			login() {
				if (this.color == '#d8d8d8') {
					uni.showToast({
						title: '请输用户名与密码',
						icon: 'none'
					})
				} else {
					console.log(this.loginAccount, this.loginPassword);
					uni.showToast({
						title: 'ok',
						icon: 'success'
					})

				}
			},
			check() {
				if (this.loginAccount.length > 0 && this.loginPassword.length > 0) {
					this.color = '#3c9cff'
				} else {
					this.color = '#d8d8d8'
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
		background: #f8f8f8;
	}

	.logo-box {
		padding: 60rpx 0;
		text-align: center;
	}

	.form-box {
		width: 90vw;
		margin: 0 auto;

		.login-btn {
			margin-top: 60rpx;
		}
	}

	.register {
		color: #cdccd1;
		margin: 0 30vw;
		padding-top: 20rpx;
	}
</style>