<template>
	<view class="content">
		<view class="img">
			<image src="../../static/logo.png" class="logo" mode="aspectFill"></image>
			<image src="../../static/name.png" class="name" mode="aspectFit"></image>
		</view>
		<view class="login">
			<u-field  v-model="phone" label="手机号" placeholder="请填写手机号" icon="phone"></u-field>
			<u-field v-model="password" label="密码" placeholder="请填写密码" icon="bag" :password="true"></u-field>
			<view class="lian" @click="show">联系管理员</view>
		</view>
		<view class="btn" @click="login">员工登录</view>
		<u-popup v-model="show1" mode="center" class="" :closeable="true">
			<view class="popup" >
				<image src="../../static/admin.png" class="admin_img" mode="aspectFit"></image>
				<view class="admin-desc">长按识别二维码,添加管理员</view>
			</view>
			
		</u-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				phone:'',
				password:'',
				show1:false
			}
		},
		onLoad() {

		},
		methods: {
			//登录
			login:function(e){
				let phone = this.phone;
				let password =this.password;
				if(!phone){
					uni.showToast({
					    title: '请填写手机号',
					    duration: 2000,
						icon:'none'
					});
					return false;
				}
				if(!password){
					uni.showToast({
					    title: '请填写密码',
					    duration: 2000,
						icon:'none'
					});
					return false;
				}
				uni.reLaunch({
					url:"/pages/user/index"
				})
			},
			show:function(e){
				this.show1 = true
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
	}
	.img{
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		margin-top: 30rpx;
	}
	.logo{
		width: 300rpx;
		height: 180rpx;
	
	}
	.name{
		width: 400rpx;
		height: 200rpx;
		margin-top: -30rpx;
	}
	.login{
		width: 80%;
		margin-top: 30rpx;
	}
	.lian{
		text-align: right;
		font-size: 28rpx;
		color: #222222;
		margin-top: 15rpx;
	}
	.btn{
		margin-top: 150rpx;
		width: 50%;
		text-align: center;
		height: 80rpx;
		line-height: 80rpx;
		background: #038B2C;
		font-size: 30rpx;
		color: #FFFFFF;
		border-radius: 50rpx;
	}
	.popup{
		margin: 20rpx;
		width: 400rpx;
		height: 400rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	
	}
	.admin_img{
		width: 250rpx;
		height: 250rpx;
	}
	.admin-desc{
		font-size: 28rpx;
		margin-top: 20rpx;
	}
</style>
