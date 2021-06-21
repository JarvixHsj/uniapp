<template>
	<view>
		<image src="../../static/shanchu/Rectangle.png" mode="" style="width: 100vw; height: 99vh;"></image>
		<view class="btn" @click="getIndex">
			<text style="margin-right: 8rpx;">{{time}}s</text>跳过
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				time:3,//倒计时
			}
		},
		onLoad() {
			let that = this;
			setInterval(()=>{
				that.time -= 1;
				if(that.time == 0) {
					uni.switchTab({
						url:'./index'
					})
				}
			},1000)
		},
		methods: {
			getIndex() {
				uni.switchTab({
					url:'./index'
				})
			},
		}
	}
</script>

<style>
	.btn {
		position: fixed;
		right: 32rpx;
		top: 110rpx;
		width: 138rpx;
		height: 64rpx;
		opacity: 1;
		background: rgba(0,0,0,0.40);
		border-radius: 46rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		color: #FFFFFF;
		font-size: 26rpx;
		
	}
</style>
