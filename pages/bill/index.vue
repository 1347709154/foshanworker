<template>
	<view class="content">
		<view class="card">
			<view class="card-tetl">
				<view class="">佛顶山旅游景区</view>
				<image src="../../static/scenic_inc.png"></image>
			</view>
			<u-field  type="text"  label="姓名:" placeholder="请输入姓名"></u-field>
			<u-field  type="idcard"  label="身份证:" placeholder="请输入身份证号"></u-field>
			<u-field  type="text"  label="日期:" placeholder="请输入购票有效期"></u-field>
			<u-field  type="number"  label="电话:" placeholder="请输入联系电话"></u-field>
			<u-field  type="digit"  label="票价:" placeholder="请输入票价"></u-field>
		</view>
		<view class="Submit">提交</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	page{
		background: #F4F7F8;
	}
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.card{
		width: 100%;
		background: #FFFFFF;
		margin-top: 40rpx;
		padding: 0rpx 32rpx;
		padding-bottom: 30rpx;
	}
	.card-tetl{
		display: flex;
		flex-direction: row;
		align-items: flex-end;
		margin-top: 30rpx;
		font-size: 32rpx;
		font-weight: bold;
		margin-bottom: 20rpx;
	}
	.card-tetl>image{
		width: 45rpx;
		height: 45rpx;
		margin-left: 10rpx;
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
