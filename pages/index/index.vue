<template>
	<view class="content">
		<!-- 头部 -->
		<view class="header">
			<view class="header_l">
				<view class="city">
					<image :src="imageUrl+'ic_loc.png'" mode="" style="width: 32rpx; height: 32rpx;"></image>
					<text style="color: #323233; font-size: 28rpx; font-weight: 700; margin-left: 4rpx;">天津</text>
				</view>
				<view class="concreteness">
					<text>鑫茂科技园</text>
					<image :src="imageUrl + 'ic_arrow.png'" mode="" style="width: 24rpx; height: 24rpx;"></image>
				</view>
			</view>
			<view class="header_r">
				<image :src="imageUrl+'ic_mess.png'" mode="" style="width: 48rpx; height: 48rpx;"></image>
				<view class="num">
					28
				</view>
			</view>
		</view>
		<!-- 搜索 -->
		<view class="search">
			<image :src="imageUrl + 'ic-search.png'" mode="" style="width: 32rpx; height: 32rpx;margin-right: 8rpx;">
			</image>
			<text style="color: #969799; opacity: 0.8; font-size: 28rpx;">搜索商品</text>
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

		<!-- 切换部分 -->
		<view class="cut">
			<!-- 轮播 -->
			<view class="wrap">
				<u-swiper :list="listSw" mode='dot' border-radius=24 height=280></u-swiper>
			</view>
			<!-- 推荐模块 -->
			<view class="modules">
				<view class="modules_l">
					<view class="modules_l_header">
						<text style="color: #323233; font-size: 30rpx; font-weight: 700;">团购专区</text>
						<view class="modules_l_header_r">
							万千好物
						</view>
					</view>
					<view class="modules_l_base">
						<image :src="imageUrl+ 'Rectangle 2372.png'" mode="" style="width: 136rpx; height: 136rpx;">
						</image>
						<image :src="imageUrl+ 'Rectangle 2372.png'" mode="" style="width: 136rpx; height: 136rpx;">
						</image>
					</view>
				</view>
				<view class="modules_r">
					<view class="modules_l_header">
						<text style="color: #323233; font-size: 30rpx; font-weight: 700;">私人定制</text>
						<view class="modules_r_header_r">
							与众不同
						</view>
					</view>
					<view class="modules_l_base">
						<image :src="imageUrl+ 'Rectangle 2372.png'" mode="" style="width: 136rpx; height: 136rpx;">
						</image>
						<image :src="imageUrl+ 'Rectangle 2372.png'" mode="" style="width: 136rpx; height: 136rpx;">
						</image>
					</view>
				</view>
			</view>
		</view>

		<!-- 周边商店 -->
		<view class="shop">
			<view class="shop_l">
				<text style="color: #323233;font-size: 32rpx; font-weight: 700;">周边商店</text>
				<text style="color: #969799; font-size: 24rpx; margin-left: 16rpx;">优质好店</text>
			</view>
			<view class="shop_r">
				更多
				<image :src="imageUrl +'ic_arrow__n@2x.png'" mode="" style="width: 32rpx; height: 32rpx;"></image>
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
						促销
					</view>
					<view class="zhe_list">
						团购
					</view>
				</view>
				<view class="zhe_base">
					<text style="color: #969799; font-size: 24rpx;">新顺北大街10号西60米</text>
					<view class="zhe_base_r">
						<text style="color: #323233; font-size: 20rpx; margin-right: 8rpx;">2.8m</text>
						<image :src="imageUrl +'ic_daohang@2x.png'" mode="" style="width: 48rpx; height: 48rpx;"></image>
					</view>
				</view>
			</view>
		</view>
		<!-- 好物推荐 -->
		<view class="article">
			<text style="color: #323233; font-size: 32rpx; font-weight: 700;">好物推荐</text>
			<text style="color: #969799; font-size: 24rpx; margin-left: 16rpx;">为你专属</text>
		</view>
		<view class="article_conent">
			<view class="article_conent_list">
				<image :src="imageUrl +'Rectangle 2372.png'" mode="" style="width: 334rpx; height: 334rpx;"></image>
				<view class="article_conent_list_base">
					<view class="article_conent_list_base_t">
						YSL圣罗兰年春夏 女士 夹克刺绣丝绒
					</view>
					<view class="article_conent_list_base_c">
						<text style="color: #FF2F2F;font-size: 24rpx;font-weight: 600;">¥</text><text style="color: #FF2F2F; font-size: 28rpx; font-weight: 600;">288.90</text><text style="color: #C8C9CC; font-size: 22rpx; margin-left: 8rpx;">已售256</text>
					</view>
					<view class="article_conent_list_base_b">
						¥368.90
					</view>
				</view>
			</view>
			<view class="article_conent_list">
				<image :src="imageUrl +'Rectangle 2372.png'" mode="" style="width: 334rpx; height: 334rpx;"></image>
				<view class="article_conent_list_base">
					<view class="article_conent_list_base_t">
						YSL圣罗兰年春夏 女士 夹克刺绣丝绒
					</view>
					<view class="article_conent_list_base_c">
						<text style="color: #FF2F2F;font-size: 24rpx;font-weight: 600;">¥</text><text style="color: #FF2F2F; font-size: 28rpx; font-weight: 600;">288.90</text><text style="color: #C8C9CC; font-size: 22rpx; margin-left: 8rpx;">已售256</text>
					</view>
					<view class="article_conent_list_base_b">
						¥368.90
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
				title: 'Hello',
				state: 0,
				list: [
					'推荐',
					'时尚运动',
					'精品男装',
					'时尚女装',
					'电子数码'
				],
				listSw: [{
						image: 'https://cdn.uviewui.com/uview/swiper/1.jpg',
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
					}
				]
			}
		},
		onLoad() {

		},
		onPullDownRefresh() {
			let that = this;
			setTimeout(function() {
				uni.stopPullDownRefresh();
			}, 1000);
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
		padding-bottom: 32rpx;
	}

	.content {
		width: 100%;

		box-sizing: border-box;
		padding: 0 32rpx;
		padding-top: 90rpx;
	}

	.header {
		width: 100%;
		height: 88rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.header_l {
		display: flex;
		align-items: center;
	}

	.city {
		display: flex;
		align-items: center;
	}

	.concreteness {
		display: flex;
		align-items: center;
		margin-left: 32rpx;
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

	.search {
		width: 100%;
		height: 64rpx;
		opacity: 1;
		background: #f2f3f5;
		border-radius: 88rpx;
		display: flex;
		align-items: center;
		justify-content: center;
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

	.cut {
		width: 100%;
		margin-top: 34rpx;
	}

	.wrap {
		width: 100%;
		height: 280rpx;
		border-radius: 24rpx;
	}

	.modules {
		margin-top: 24rpx;
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.modules_l {
		width: 334rpx;
		height: 228rpx;
		opacity: 1;
		background: linear-gradient(180deg, #fff2f2, #ffffff 100%);
		border-radius: 24rpx;
		box-sizing: border-box;
		padding: 24rpx;
	}

	.modules_r {
		width: 334rpx;
		height: 228rpx;
		opacity: 1;
		background: #FFFFFF;
		border-radius: 24rpx;
		box-sizing: border-box;
		padding: 24rpx;
	}

	.modules_l_header {
		display: flex;
		align-items: center;
	}

	.modules_l_header_r {
		width: 104rpx;
		height: 32rpx;
		opacity: 1;
		background: linear-gradient(90deg, #f62a26 0%, #fe9288 100%);
		border-radius: 6rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		color: #FFFFFF;
		font-size: 20rpx;
		margin-left: 8rpx;
	}

	.modules_r_header_r {
		width: 104rpx;
		height: 32rpx;
		opacity: 1;
		background: linear-gradient(269deg, #f0bea1 0%, #cc8862 100%);
		border-radius: 6rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		color: #FFFFFF;
		font-size: 20rpx;
		margin-left: 8rpx;
	}

	.modules_l_base {
		margin-top: 8rpx;
		display: flex;
		align-items: center;
	}

	.shop {
		margin-top: 50rpx;
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.shop_r {
		display: flex;
		align-items: center;
		color: #323233;
		font-size: 24rpx;
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
	.article {
		margin-top: 40rpx;
		margin-bottom: 24rpx;
	}
	.article_conent {
		width: 100%;
		display: flex;
		align-items: center;
		flex-wrap: wrap;
		justify-content: space-between;
	}
	.article_conent_list {
		width: 334rpx;
		height: 531rpx;
		background: #FFFFFF;
		border-radius: 16rpx;
	}
	.article_conent_list_base {
		width: 100%;
		height: 198rpx;
		box-sizing: border-box;
		padding: 20rpx;
	}
	.article_conent_list_base_t {
		color: #323233;
		font-size: 28rpx;
		
	}
	.article_conent_list_base_c {
		margin: 10rpx;
	}
	.article_conent_list_base_b {
		color: #C8C9CC;
		font-size: 22rpx;
		text-decoration: line-through;
	}
</style>
