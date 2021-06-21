<template>
	<view>
		<view class="header">
			<view class="header_city">
				<image src="../../static/image/ic_loc.png" mode="" style="width: 32rpx; height: 32rpx;"></image>
				<text style="color: #323233; font-size: 28rpx; font-weight: 700;">天津</text>
			</view>
			<view class="seach">
				<image src="../../static/image/ic-search.png" mode="" style="width: 32rpx; height: 32rpx;"></image>
				<text style="color: #969799;font-size: 28rpx; margin-left: 11rpx;">搜索商品</text>
			</view>
			<view class="header_r">
				<image src="../../static/image/ic_mess.png" mode="" style="width: 48rpx; height: 48rpx;"></image>
				<view class="num">
					28
				</view>
			</view>
		</view>
		<!-- 推荐 -->
		<view class="recommend">
			<view class="recommend_l">
				<view :class="['list',index==state?'list_style':'']" v-for="(item,index) in list" :key="index"
					@click="getState(index)">
					{{item}}
				</view>
		
			</view>
			<view class="recommend_r">
				<image :src="imageUrl+ 'ic_filter2.png'" mode=""
					style="width: 32rpx; height: 32rpx; margin-right: 4rpx;"></image>
				分类
			</view>
		</view>
		<!-- 商店列表 -->
		<view class="shop_list">
			<view class="shop_list_l">
				<image :src="imageUrl +'Rectangle 2372.png'" mode="" style="width: 152rpx; height: 152rpx;"></image>
			</view>
			<view class="shop_list_r">
				<view class="shop_list_r_t">
					<text class="k">加盟</text>
					<text class="y">优衣库 (永旺梦乐城益麒家居优衣库 (永旺梦乐城益麒家居...</text>
				</view>
				<view class="zhe">
					<view class="zhe_list">
						折扣
					</view>
				</view>
				<view class="zhe_base">
					<text style="color: #969799; font-size: 24rpx;">新顺北大街10号西60米</text>
					<view class="zhe_base_r">
						<text style="color: #323233; font-size: 20rpx; margin-right: 8rpx;">500m</text>
						<image :src="imageUrl +'ic_daohang@2x.png'" mode="" style="width: 48rpx; height: 48rpx;"></image>
					</view>
				</view>
			</view>
		</view>
		<view class="shop_list">
			<view class="shop_list_l">
				<image :src="imageUrl +'Rectangle 2372.png'" mode="" style="width: 152rpx; height: 152rpx;"></image>
			</view>
			<view class="shop_list_r">
				<view class="shop_list_r_t">
					<text class="k">加盟</text>
					<text class="y">优衣库 (永旺梦乐城益麒家居优衣库 (永旺梦乐城益麒家居...</text>
				</view>
				<view class="zhe">
					<view class="zhe_list">
						折扣
					</view>
					<view class="zhe_list">
						团购
					</view>
				</view>
				<view class="zhe_base">
					<text style="color: #969799; font-size: 24rpx;">新顺北大街10号西60米</text>
					<view class="zhe_base_r">
						<text style="color: #323233; font-size: 20rpx; margin-right: 8rpx;">500m</text>
						<image :src="imageUrl +'ic_daohang@2x.png'" mode="" style="width: 48rpx; height: 48rpx;"></image>
					</view>
				</view>
			</view>
		</view>
		<view class="shop_list">
			<view class="shop_list_l">
				<image :src="imageUrl +'Rectangle 2372.png'" mode="" style="width: 152rpx; height: 152rpx;"></image>
			</view>
			<view class="shop_list_r">
				<view class="shop_list_r_t">
					<text class="k" style="background: linear-gradient(90deg,#eb3928 58%, #f67343 100%);">直营</text>
					<text class="y">优衣库 (永旺梦乐城益麒家居优衣库 (永旺梦乐城益麒家居...</text>
				</view>
				<view class="zhe">
					<view class="zhe_list">
						折扣
					</view>
					<view class="zhe_list">
						促销
					</view>
				</view>
				<view class="zhe_base">
					<text style="color: #969799; font-size: 24rpx;">新顺北大街10号西60米</text>
					<view class="zhe_base_r">
						<text style="color: #323233; font-size: 20rpx; margin-right: 8rpx;">500m</text>
						<image :src="imageUrl +'ic_daohang@2x.png'" mode="" style="width: 48rpx; height: 48rpx;"></image>
					</view>
				</view>
			</view>
		</view>
		<view class="shop_list">
			<view class="shop_list_l">
				<image :src="imageUrl +'Rectangle 2372.png'" mode="" style="width: 152rpx; height: 152rpx;"></image>
			</view>
			<view class="shop_list_r">
				<view class="shop_list_r_t">
					<text class="k">加盟</text>
					<text class="y">优衣库 (永旺梦乐城益麒家居优衣库 (永旺梦乐城益麒家居...</text>
				</view>
				<view class="zhe">
					<view class="zhe_list">
						折扣
					</view>
				</view>
				<view class="zhe_base">
					<text style="color: #969799; font-size: 24rpx;">新顺北大街10号西60米</text>
					<view class="zhe_base_r">
						<text style="color: #323233; font-size: 20rpx; margin-right: 8rpx;">500m</text>
						<image :src="imageUrl +'ic_daohang@2x.png'" mode="" style="width: 48rpx; height: 48rpx;"></image>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import app from '../../App.vue'
	export default {
		data() {
			return {
				imageUrl: app.globalData.imageUrl,
				state: 0,
				list: [
					'推荐',
					'时尚运动',
					'精品男装',
					'时尚女装',
					'电子数码'
				],
			}
		},
		methods: {
			//切换状态
			getState(i) {
				let that = this;
				that.state = i;
			},
		}
	}
</script>

<style>
 page {
	background: #F7F8FA;
	 box-sizing: border-box;
	 padding: 0 32rpx;
	 padding-top: 100rpx;
	 
 }
 .header {
	 width: 100%;
	 display: flex;
	 align-items: center;
 }
 .header_city {
	 display: flex;
	 align-items: center;
 }
 .seach {
	 width: 482rpx;
	 height: 64rpx;
	 opacity: 1;
	 background: #f2f3f5;
	 border-radius: 88rpx;
	 display: flex;
	 align-items: center;
	 justify-content: center;
	 margin-left: 30rpx;
	 margin-right: 36rpx;
 }
 
 .header_r {
 	position: relative;
 }
 
 .num {
 	position: absolute;
 	right: -10rpx;
 	top: -20rpx;
 	background: #F35333;
 	font-size: 20rpx;
 	color: #FFFFFF;
 	border-radius: 18rpx;
 	padding: 2rpx 8rpx;
 }
 .recommend {
 	margin-top: 20rpx;
 	width: 100%;
 	height: 88rpx;
 	display: flex;
 	align-items: center;
 	justify-content: space-between;
 	border-bottom: 2rpx solid rgba(242, 243, 245, 0.8);
 }
 
 .recommend_l {
 	width: calc(100% - 128rpx);
 	height: 100%;
 	display: -webkit-box;
 	align-items: center;
 	overflow: hidden;
 	overflow-x: auto;
 	/* background: rgba(151,151,151,0.1); */
 }
 
 .list {
 	/* width: 138rpx; */
 	text-align: center;
 	color: #323233;
 	font-size: 28rpx;
 	margin-right: 26rpx;
 }
 
 ::-webkit-scrollbar {
 	display: none;
 	/* Chrome Safari */
 }
 
 .recommend_r {
 	width: 128rpx;
 	height: 100%;
 	display: flex;
 	align-items: center;
 	justify-content: center;
 	box-shadow: 15rpx, linear-gradient(0deg, rgba(0, 0, 0, 0.04) 0%, rgba(0, 0, 0, 0.00) 100%);
 }
 
 .list_style {
 	/* width: 138rpx; */
 	position: relative;
 	color: #323233;
 	font-size: 36rpx;
 	font-weight: 700;
 }
 
 .list_style::after {
 	position: absolute;
 	left: 50%;
 	transform: translateX(-50%);
 	bottom: -18rpx;
 	content: '';
 	width: 48rpx;
 	height: 6rpx;
 	background: #EE0A24;
 	border-radius: 28rpx;
 }
 .shop_list {
 	margin-top: 16rpx;
 	width: 100%;
 	height: 216rpx;
 	opacity: 1;
 	background: #ffffff;
 	border-radius: 24rpx;
 	box-sizing: border-box;
 	padding: 32rpx 24rpx;
 	display: flex;
 	align-items: center;
 }
 
 .shop_list_r {
 	width: calc(100% - 160rpx);
 	height: 152rpx;
 	display: flex;
 	flex-direction: column;
 	/* justify-content: space-between; */
 }
 
 .shop_list_r_t {
 	width: 100%;
 	display: flex;
 	align-items: center;
 
 
 }
 
 .k {
 	display: inline-block;
 	width: 56rpx;
 	height: 32rpx;
 	opacity: 1;
 	background: linear-gradient(90deg, #ffa825 58%, #ffc148 100%);
 	border-radius: 4rpx;
 	color: #FFFFFF;
 	font-size: 20rpx;
 	display: flex;
 	align-items: center;
 	justify-content: center;
 	margin-right: 8rpx;
 }
 
 .y {
 	width: calc(100% - 56rpx);
 	display: -webkit-box;
 	overflow: hidden;
 	text-overflow: ellipsis;
 	word-wrap: break-word;
 	white-space: normal !important;
 	-webkit-line-clamp: 1;
 	-webkit-box-orient: vertical;
 }
 .zhe {
 	width: 100%;
 	display: flex;
 	align-items: center;
 	margin-top: 22rpx;
 	margin-bottom: 16rpx;
 }
 .zhe_list {
 	margin-right: 8rpx;
 	width: 56rpx;
 	height: 28rpx;
 	opacity: 1;
 	border: 1rpx solid #f35333;
 	border-radius: 5rpx;
 	color: #F35333;
 	font-size: 20rpx;
 	display: flex;
 	align-items: center;
 	justify-content: center;
 }
 .zhe_base {
 	width: 100%;
 	display: flex;
 	align-items: center;
 	justify-content: space-between;
 }
 .zhe_base_r {
 	display: flex;
 	align-items: center;
 }
</style>
