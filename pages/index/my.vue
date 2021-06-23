<template>
	<view>
		<view class="conent">
			<view class="content-bg"> 
				<view class="flex flex-justify-between change">
					<view>切换商家</view>
					<view>
						<u-image src="../../static/image/user/ic_set.png" width="50rpx" height="50rpx"></u-image>
					</view>
				</view>
			</view> 
			<view class="order">
				<view class="my-order flex flex-justify-between">
					<view class="orderText">我的订单</view>
					<view class="more">查看全部
						<u-icon name="arrow-right" color="#C8C9CC" size="28"></u-icon>
					</view>
				</view>
				<view class="flex order-data">
					<view v-for="item in orderData" :key="item.id" class="order-item">
						<view class="tips">
							<u-badge type="error" :count="item.count" is-center size="mini" ></u-badge>
							<u-image width="50rpx" height="50rpx" :src="item.src"></u-image>
						</view>
						<view>{{item.name}}</view>
					</view>
				</view>
			</view>
			<view class="project">

			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				orderData:[
					{id:1,name:"待支付",src:"../../static/image/user/ic_paid.png",count:"7"},
					{id:1,name:"待发货",src:"../../static/image/user/ic_delivered.png",count:"28"},
					{id:1,name:"待支付",src:"../../static/image/user/ic_receipt.png",count:"0"},
					{id:1,name:"待支付",src:"../../static/image/user/ic_sale.png",count:"0"},
					{id:1,name:"待支付",src:"../../static/image/user/ic_group_oder.png",count:"0"},
				]	
			}
		},
		onShow() {
			// setTimeout(()=>{
			// 	uni.redirectTo({
			// 		url:'../login/login'
			// 	})
			// },250)
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
.conent {
	position: relative;
	width: 100%;
	height: 100vh;
	background: #F7F8FA;
	.content-bg{
		width: 100%;
		border-radius: 0px;
		position: absolute;
		left: 0px;
		right: 0px;
		top: 0px;
		bottom: 0px;
		background: url("../../static/image/user/img_my_bg.png") no-repeat;
		.change{
			margin:  7rpx 4rpx 7rpx 44rpx;
		}
	}
	.order{
		position: absolute;
		width: 343px;
		height: 122px;
		left: 16px;
		top: 210px;
		background: #FFFFFF;
		border-radius: 12px;
		.my-order{
			margin: 24rpx 40rpx  40rpx  40rpx;
			.orderText{
				font-family: PingFang SC;
				font-style: normal;
				font-weight: 500;
				font-size: 14px;
				line-height: 18px;
			}
			.more{
				color: #969799;
			}
		}
		.order-data{
			margin: 0rpx 24rpx 40rpx 24rpx;
			.order-item{
				flex: 1;
				text-align: center;
			}
			.tips{
				position: relative;
				margin: 0 auto;
				display: block;
				width: 50rpx;
				height: 50rpx;
			}
		}

	}
	.project{
		position: absolute;
		width: 343px;
		height: 219px;
		left: 16px;
		top: 350px;
		background: #FFFFFF;
		border-radius: 12px;
	}
}
</style>
