<template>
	<view class="content">
		<view class="top">我的</view>
		<view class="card" style="margin-top: 140rpx;">
			<view class="card-img">
				<image src="../../static/user_img.png"></image>
			</view>
			<view class="card-name">
				<view class="">
					<view style="font-size: 36rpx;font-weight: bold;">Rahal</view>
					<view style="color: #7B7B7B;">账号：GUY356895</view>
				</view>
				<view class="card-bt" @click="data">
					编辑资料
				</view>
			</view>
		</view>
		<view class="card">
			<view class="card-ul" @click="scanCode">
				<image src="../../static/sao.png" mode="aspectFit"></image>
				<view>扫码核验</view>
			</view>
			<view class="card-ul">
				<image src="../../static/scen.png" mode="aspectFit"></image>
				<picker @change="bindPickerChange" :value="index" :range="list" class="card-pick">
					<view @click="choices" style="float: left;color: #1F1F1F;font-size: 28rpx;">{{list[index]}}</view> 
					<u-icon v-if="choice==false" @click="choices" name="arrow-down-fill" color="#1F1F1F" size="35" style="margin-left: 5rpx;"></u-icon>
					<u-icon v-if="choice==true" @click="choices" name="arrow-up-fill" color="#1F1F1F" size="35" style="margin-left: 5rpx;"></u-icon>
				</picker>
				
			</view>
		</view>
		<view class="card" style="padding: 50rpx 32rpx;">
			<view class="card-ul" @click="bill">
				<image src="../../static/data.png" mode="aspectFit"></image>
				<view>票据录入</view>
			</view>
			<view class="card-ul" @click="record">
				<image src="../../static/lu.png" mode="aspectFit"></image>
				<view>录入记录</view>
			</view>
		</view>
		<view class="phone">联系电话：88888888</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				choice:false,
				index: 0,
				list:['景点-1','景点-2','景点-3','景点-4','景点-5','景点-6']
			}
		},
		onLoad() {

		},
		methods: {
			//箭头方向切换
			choices:function(){
				this.choice = !this.choice
			},
			//选择景点
			 bindPickerChange: function(e) {
				//console.log('picker发送选择改变，携带值为', e.target.value)
				this.index = e.target.value,
				this.choice = false
			},
			//跳转资料编辑
			data:function(){
				uni.navigateTo({
					url:"/pages/data/index"
				})
			},
			//跳转票据录入
			bill:function(){
				uni.navigateTo({
					url:"/pages/bill/index"
				})
			},
				//跳转录入记录
			record:function(){
				uni.navigateTo({
					url:"/pages/record/index"
				})
			},
			//扫码核验
			scanCode:function(){
				// uni.scanCode({
				//     success: function (res) {
				//         console.log('条码类型：' + res.scanType);
				//         console.log('条码内容：' + res.result);
				//     }
				// });
			}
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
	.top{
		width: 100%;
		text-align: center;
		height: 100rpx;
		line-height: 100rpx;
		background: #FFFFFF;
		position: fixed;
		top: 0rpx;
		left: 0rpx;
		z-index: 9;
		color: #1F1F1F;
		font-size: 32rpx;
	}
	.card{
		width: 96%;
		background: #FFFFFF;
		border-radius: 20rpx;
		margin-top: 40rpx;
		padding: 30rpx 32rpx;
		display: flex;
		flex-direction: row;
		
	}
	.card-img{
		text-align: center;
	}
	.card-img>image{
		width: 150rpx;
		height: 150rpx;
		border-radius: 50%;
	}
	.card-name{
		width: 100%;
		padding-left: 10rpx;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
	}
	.card-bt{
		width: 150rpx;
		text-align: center;
		line-height: 50rpx;
		color: #FFFFFF;
		width: 150rpx;
		height: 50rpx;
		background: #21A248;
		font-size: 28rpx;
		border-radius: 20rpx;
	}
	.card-ul{
		width: 50%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.card-ul>image{
		width: 100rpx;
		height: 100rpx;
	}
	.card-pick{
		width: 100%;
		margin-top: 10rpx;
		color: #1F1F1F;
		font-size: 28rpx;
		float: left;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
	.card-pick>view{
		float: left;
	}
	.phone{
		margin-top: 50rpx;
		color: #D9D9D9;
	}
	.popup-box{
		padding-top: 50rpx;
	}
	.popup{
		margin-top: 50rpx;
		padding-bottom: 20rpx;
		border-bottom: 1rpx solid #ddd;
		width: 100%;
		text-align: center;
	
	}
</style>
