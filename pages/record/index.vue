<template>
	<view class="content">
		<view class="list" v-for="(item,index) in list">
			<view class="list-l">
				<view class="name" style="font-size: 32rpx;font-weight: bold;">{{item.user_name}}</view>
				<view class="name">有限期至{{item.time}}</view>
				<view class="name">{{item.user_phone}}</view>
				<view class="name">{{item.user_ID}}</view>
			</view>
			<view class="list-r">
				<view class="money">
					¥<text style="font-size: 40rpx;padding: 0rpx 5rpx;">{{item.money}}</text>元
				</view>
				<view class="type">{{item.type}}</view>
			</view>
		</view>
		<view class="null">没有更多了~</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[
					{
						user_name :'李白',
						time:'2021-06-29',
						user_phone: '15186107585',
						user_ID : '123456789123123456789',
						money:36,
						type:'佛顶山景区'
					},{
						user_name :'李白',
						time:'2021-06-29',
						user_phone: '15186107585',
						user_ID : '123456789123123456789',
						money:36,
						type:'佛顶山景区'
					}
				]
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
	.list{
		width: 94%;
		border-radius: 30rpx;
		background: #FFFFFF;
		margin-top: 40rpx;
		padding: 40rpx 20rpx;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}
	.list-l{
		margin-left: 10rpx;
		width: 70%;
	}
	.list-r{
		text-align: right;
	}
	.name{
		font-size: 28rpx;
		color: #161616;
		margin-bottom: 20rpx;
	}
	.money{
		margin-top: 50rpx;
		color: #F50909;
		font-size: 30rpx;
		font-weight: bold;
	}
	.type{
		margin-top: 80rpx;
		font-size: 28rpx;
		color: #2E2E2E;
	}
	.null{
		margin-top: 50rpx;
		color: #D9D9D9;
		font-size: 26rpx;
	}
</style>
