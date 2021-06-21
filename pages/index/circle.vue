<template>
	<view>
		<view class="header">
			<view class="seach">
				<image src="../../static/image/ic-search.png" mode="" style="width: 32rpx;height: 32rpx;"></image>
				<text style="color: #969799; font-size: 28rpx; margin-left: 11rpx;">搜索话题关键字</text>
			</view>
			<view class="header_conent">
				<view :class="['header_conent_l',sta==0?'sty':'' ]" @click="getSta(0)">
					推荐
				</view>
				<view :class="['header_conent_l',sta==1?'sty':'' ]" style="margin-left: 64rpx;" @click="getSta(1)">
					我加入的
				</view>
			</view>
		</view>
		
		<!-- 内容 -->
		<view class="list" v-if="sta == 0">
			<view class="list_header">
				<image src="../../static/image/ic_groupmanagement@2x.png"  mode="" style="width: 72rpx; height: 72rpx; border-radius: 50%;"></image>
				<view class="list_header_r">
					<view class="t">
						草草
					</view>
					<view class="b">
						2021-05-18 08:52
					</view>
				</view>
				
			</view>
			<view class="conent">
				我捡了个神灯，许愿我死前能找到女朋友，结果我获得了永生！
			</view>
			<view class="conent_base">
				蹲下来摸摸自己的影子，对不起，跟着我让你受委屈了。
			</view>
			<view class="base">
				<view class="base_list">
					<image src="../../static/image/ic_hert_n@2x.png" mode="" style="width: 40rpx; height: 40rpx;margin-right: 10rpx;"></image>
					<text>33</text>
				</view>
				<view class="base_list">
					<image src="../../static/image/icon_comment@2x.png" mode="" style="width: 40rpx; height: 40rpx;margin-right: 10rpx;"></image>
					<text>150</text>
				</view>
				<view class="base_list"> 
					<image src="../../static/image/icon_fabulous_n@2x.png" mode="" style="width: 40rpx; height: 40rpx;margin-right: 10rpx;"></image>
					<text>1</text>
				</view>
			</view>
		</view>
		
		<!-- 我加入的 -->
		<view class="coo" v-else-if="sta == 1">
			<view class="coo_top">
				圈子博主
			</view>
			<view class="coo_connet">
				<view class="list_header">
					<image src="../../static/image/ic_groupmanagement@2x.png"  mode="" style="width: 72rpx; height: 72rpx;"></image>
					<view class="list_header_r">
						<view class="t" style="font-size: 500;">
							今天穿什么
						</view>
						<view class="b">
							GUCCL
						</view>
					</view>
					
				</view>
				<view class="l">
					俄罗斯方块教会我们：如果你合群，就会消失。
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				sta:0,
			}
		},
		methods: {
			getSta(i) {
				let that = this;
				that.sta = i
			},
		}
	}
</script>

<style>
	page {
		background: #F7F8FA;
		 box-sizing: border-box;
		 /* padding: 0 32rpx; */
		
		 
	}
	.header {
		width: 100%;
		box-sizing: border-box;
		padding: 0 32rpx;
		padding-top: 100rpx;
		background: #FFFFFF;
	}
	.seach {
		width: 100%;
		height: 64rpx;
		opacity: 1;
		background: #f2f3f5;
		border-radius: 88rpx;
		display: flex;
		align-items: center;
		box-sizing: border-box;
		padding-left: 26rpx;
	}
	.header_conent {
		width: 100%;
		height: 88rpx;
		margin-top: 12rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.header_conent_l {
		color: #323233;
		font-size: 28rpx;
		
	}
	.sty {
		position: relative;
		font-size: 36rpx;
		font-weight: 700;
		color: #323233;
	}
	.sty::after {
		content: '';
		position: absolute;
		left: 50%;
		transform: translateX(-50%);
		bottom: -15rpx;
		width: 48rpx;
		height: 6rpx;
		background: #eb1b34;
		border-radius: 28rpx;
	}
	.list {
		margin-top: 24rpx;
		background: #FFFFFF;
		border-radius: 24rpx;
		padding: 32rpx;
		display: flex;
		flex-direction: column; 
	}
	.list_header {
		display: flex;
		
	}
	.list_header_r {
		height: 72rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		margin-left: 16rpx;
	}
	.t {
		color: #323233;
		font-size: 28rpx;
		font-weight: 600;
	}
	.b {
		color: #969799;
		font-size: 20rpx;
	}
	.conent {
		color: #323233;
		font-size: 28rpx;
		font-weight: 600;
		margin-top: 24rpx;
	}
	.conent_base {
		margin-top: 8rpx;
		color: #969799;
		font-size: 26rpx;
	}
	.base {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-around;
		margin-top: 28rpx;
	}
	.base_list {
		display: flex;
		align-items: center;
		color: #323233;
		font-size: 22rpx;
	}
	.coo {
		width: 100%;
		box-sizing: border-box;
		padding: 0 32rpx;
	}
	.coo_top {
		width: 100%;
		margin-top: 34rpx;
		display: flex;
		height: 106rpx;
		align-items: center;
		box-sizing: border-box;
		padding: 0 32rpx;
		color: #323233;
		font-size: 28rpx;
		font-weight: 700;
		background: #FFFFFF;
		border-radius: 24rpx;
	}
	.coo_connet {
		background: #FFFFFF;
		border-radius: 24rpx;
		margin-top: 32rpx;
		width: 100%;
		box-sizing: border-box;
		padding: 32rpx;
	}
	.l {
		margin-top: 26rpx;
		width: 622rpx;
		height: 64rpx;
		opacity: 1;
		background: #f7f8fa;
		border-radius: 16rpx;
		box-sizing: border-box;
		padding: 16rpx 24rpx;
		color: #969799;
		font-size: 24rpx;
	}
</style>
