<template>
	<view class="content">
		<view class="user-img">
			<image src="../../static/user_img.png" mode="scaleToFill"></image>
		</view>
		<view class="card">
			<u-field  type="text"  v-model="user_name" label="员工姓名" placeholder="请输入您的姓名"></u-field>
			<u-field  type="text"  v-model="user_ID" label="登录账号" placeholder="请输入您的账号"></u-field>
			<u-field  type="text"  v-model="user_password" label="登录密码" placeholder="请输入您的密码" :password="true"></u-field>
			<u-field  type="number"  v-model="user_phone" label="联系电话" placeholder="请输入您的联系电话"></u-field>
		</view>
		<view class="Submit">完成</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				user_name:'',
				user_ID:'',
				user_password:'',
				user_phone:'',
				
			}
		},
		onLoad() {

		},
		methods: {
			getCode:function(e){
				console.log(111111111)
			},
			radio:function(e){
				this.sex=e;
			}
		}
	}
</script>

<style>
	/* page{
		background: #F2F6F7;
	} */
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.user-img{
		width: 100%;
		background: #ffffff;
		display: flex;
		flex-direction: row;
	/* 	align-items: center; */
		justify-content: center;
		margin-top: 30rpx;
	}
	.user-img>image{
		width: 170rpx;
		height: 170rpx;
		border-radius: 50%;
	}
	.card{
		width: 100%;
		background: #ffffff;
		margin-top: 50rpx;
		padding: 0 32rpx;
	}
	.user-mobile{
		height: 80rpx;
		border-bottom: 1rpx solid #ddd;
	}
	.cell-item{
		color: #000000;
	}
	.radio{
		text-align: left;
		
	}
	.Submit{
		width: 80%;
		height: 80rpx;
		text-align: center;
		line-height: 80rpx;
		background: #038B2C;
		color: #FFFFFF;
		margin-top: 150rpx;
		border-radius: 50rpx;
	}
</style>
