<template>
	<view>
		<view class="register-box">
			<image style="height: 160rpx;width: 160rpx;" src="../../static/logo.png" mode=""></image>
			<view class="">校店注册</view>
		</view>
		<view class="form-box">
			<!-- <u--input @input='check' placeholder="请输入账号" :clearable='true' customStyle='background-color: white;' v-model="account"></u--input>
			<u--input @input='check' placeholder="请输入密码" :clearable='true' customStyle='background-color: white;margin-top: 10rpx;' :password='true' v-model="password"></u--input>
			<u--input @input='check' placeholder="请再次输入密码" :clearable='true' customStyle='background-color: white;margin-top: 10rpx;' :password='true' v-model="rePassword"></u--input> -->
			<u--form ref='uform' :model='form' :rules='rules'>
				<u-form-item prop='account' borderBottom>
					<u--input v-model="form.account" border='none' placeholder="请输入账号" @input='check' :clearable='true'></u--input>
				</u-form-item>
				<u-form-item prop='password' borderBottom>
					<u--input v-model="form.password" border='none' placeholder="请输入密码" @input='check' :type="show? 'input': 'password'" :clearable='true'>
						<template slot='suffix'>
							<u-icon @click="show=!show" :name="show1? 'eye-fill': 'eye-off'"></u-icon>
						</template>
					</u--input>
				</u-form-item>
				<u-form-item prop='rePassword' borderBottom>
					<u--input v-model="form.rePassword" border='none' placeholder="请再次输入密码" @input='check' :type="show1? 'input': 'password'" :clearable='true'>
						<template slot='suffix'>
							<u-icon @click="show1=!show1" :name="show1? 'eye-fill': 'eye-off'"></u-icon>
						</template>
					</u--input>
				</u-form-item>
				</u--form>
			<u-button  class="register-btn" text="注册" shape="circle" :color="color" @click="register" ></u-button>
		</view>
		<view class="register" @click="toLogin">
			已有账号，去登录
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:false,
				show1:false,
				form:{
					account:'',
					password:'',
					rePassword:''
				},
				// account:'',
				// password:'',
				// rePassword:'',
				color:'#d8d8d8',
				rules:{
					account:{
						type:'string',
						required:true,
						message:'请输入账号',
						trigger:['blur']
					},
					password:{
						type:'string',
						required:true,
						message:'请输入密码',
						trigger:['blur']
					},
					rePassword:[{
						type:'string',
						required:true,
						message:'请输入密码',
						trigger:['blur']
					},
					{
						validator: (rule, value, callback) => {
						return value == this.form.password
						},
						trigger:['blur','change'],
						message: '密码不一致'
					
					}]
				}
			};
		},
		methods:{
			register(){
			if(this.password!=this.rePassword){
				uni.showToast({
					title:'2次密码不一致',
					icon:'error'
				})
			}
			if(this.color=='#d8d8d8'){
				uni.showToast({
					title:'用户名或密码不能为空',
					icon:'none'
				})
			}else{
				console.log(this.form);
			}
			},
			check(){
				// this.account=this.form.account
				// this.password=this.form.password
				// this.rePassword=this.form.rePassword
				if(this.form.account.length>0&&this.form.password.length>0&&this.form.rePassword.length>0){
					this.color='#3c9cff'
				}else{
					this.color='#d8d8d8'
				}
			},
			toLogin(){
				uni.navigateTo({
					url:'/pages/login/login'
				})
			}
		}
	}
</script>

<style lang="scss">
.register-box{
	padding: 60rpx 0;
	text-align: center;
}
.form-box{
	width: 90vw;
	margin: 0 auto;
	.register-btn{
		margin-top: 60rpx;
	}
}
.register{
	color: #cdccd1;
	margin: 0 30vw;
	padding-top: 20rpx;
}
</style>
