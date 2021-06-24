<template>
  <view class="product-frame" :style="'height: ' + windowHeight">
    <view class="search-frame">
    	<view class="search-box">
    		<!-- <view class="iconfont icon-search"></view>
    		<input type="text" value="" placeholder="输入商品名称、型号、品牌查找"/> -->
        <u-search placeholder="搜索商品" input-align="center" v-model="search" :show-action="false"></u-search>
    	</view>
    </view>
		<!-- 一级分类tab栏 -->
    <!-- <view class="tab-wrap">
      <v-tabs
        v-model="current"
        :tabs="tabs"
        :bold="true"
        activeColor="#000"
        activeFontSize="40upx"
        color="#666"
        fontSize="32upx"
        @change="changeTab"></v-tabs>
    </view> -->
    <view class="product-wrap">
			<!-- 二级分类 -->
			<scroll-view class="cate-left" scroll-y="true" style="height: 100%;background-color: #F7F8FA;">
				 <view class="item-wrap">
						<view 
							v-for="(item, index) in secondCateList" 
              :key="index"
							@click="changeCate(item.id)" 
							class="item-name ellipsis"
							:class="[viewId === item.id ? 'active' : '']">热门品牌{{index + 1}}</view>
				 </view>
			</scroll-view>
			<!-- 三级分类 -->
			<scroll-view class="cate-right" scroll-with-animation :scroll-into-view="viewId" scroll-y="true" style="height: 100%;">
				<block>
					<view class="cate-content">
						<view v-for="(item, index) in thirdCateList" :id="item.id" class="sec-cate-item">
							 <view class="cate-title">热门品牌{{index + 1}}</view>
							 <view class="third-cate-wrap">
								 <view class="third-cate-item" @click="toProductList">
										<image class="product-img" src="../../static/image/ic_wechat.png" mode=""></image>
										<view class="product-name ellipsis">血细胞分析仪</view>
								 </view>
								 <view class="third-cate-item" @click="toProductList">
										<image class="product-img" src="../../static/image/ic_wechat.png" mode=""></image>
										<view class="product-name">血细胞分析仪</view>
								 </view>
								 <view class="third-cate-item" @click="toProductList">
										<image class="product-img" src="../../static/image/ic_wechat.png" mode=""></image>
										<view class="product-name">血细胞分析仪</view>
								 </view>
								 <view class="third-cate-item" @click="toProductList">
										<image class="product-img" src="../../static/image/ic_wechat.png" mode=""></image>
										<view class="product-name">血细胞分析仪</view>
								 </view>
								 <view class="third-cate-item" @click="toProductList">
										<image class="product-img" src="../../static/image/ic_wechat.png" mode=""></image>
										<view class="product-name">血细胞分析仪</view>
								 </view>
							 </view>
							 <view class="clearfix"></view>
						</view>
					</view>
				</block>
				<view class="clearfix"></view>
			</scroll-view>
		</view>
  </view>
</template>

<script>
export default{
  data () {
    return {
			windowHeight: '',
      current: 0,
      tabs: [
        '全部',
        '器械设备',
        '耗材',
        '试剂',
        '器械设备',
        '耗材',
        '试剂',
        '国内',
        '配件',
      ],
      search:"",
			secondCateList: [
				{id: 'c1'},{id: 'c2'},{id: 'c3'},{id: 'c4'},{id: 'c5'},{id: 'c6'},{id: 'c7'},{id: 'c8'},{id: 'c9'},{id: 'c10'},{id: 'c11'},{id: 'c12'},{id: 'c13'}
			],
			thirdCateList: [
				{id: 'c1'},{id: 'c2'},{id: 'c3'},{id: 'c4'},{id: 'c5'},{id: 'c6'},{id: 'c7'},{id: 'c8'},{id: 'c9'},{id: 'c10'},{id: 'c11'},{id: 'c12'},{id: 'c13'}
			],
			viewId: 'c1'
    }
  },
	onLoad() {
		const res = uni.getSystemInfoSync();
		console.log(res.windowHeight);
		this.windowHeight = res.windowHeight + 'px';
	},
  methods: {
    changeTab (index) {
      console.log(index)
    },
		changeCate (e) {
			this.viewId = e;
			console.log('viewId', this.viewId)
		},
		toProductList () {
			uni.navigateTo({
				url: 'productList'
			})
		}
  }
}
</script>

<style scoped lang="scss">
 .search-frame {
   padding: 30upx;
   display: flex;
   align-items: center;
   .search-box {
     width: 690upx;
     height: 90upx;
     padding-left: 20upx;
     font-size: 26upx;
    //  border: 1upx solid #dbdbdb;
    //  border-radius: 6upx;
    //  box-shadow: 2px 2px 2px #eee;
     display: flex;
     align-items: center;
     justify-content: center;
     .iconfont {
       font-size: 64upx;
       color: #c2c2c2;
     }
     input {
       width: 500upx;
       font-size: 26upx;
     }
   }
 }
 .tab-wrap{
   padding-bottom: 30upx;
   border-bottom: 1upx solid #E6EBF2;
	 z-index: 9;
 }
 .product-wrap{
	 position: absolute;
	 width: 100%;
	 top: 122upx;
	 bottom: 0;
	 left: 0;
   display: flex;
   .cate-left{
     width: 219upx;
     .item-wrap{
        // padding-top: 30upx;
        // padding-left: 26upx;
        // padding-right: 21upx;
        // border-right: 2upx solid #E6EBF2;
        background-color: #F7F8FA;
     }
     .item-name{
        color: #656565;
        text-align: center;
        font-size: 28upx;
        padding: 40upx 0;
        font-weight: 400;
     }
     .active{
        // width: 170upx;
        // height: 70upx;
        // line-height: 70upx;
        background: #fff;
        color: black;
        // border-radius: 35upx;
        // margin: 16upx 0;
     }
   }
   .cate-right{
      width: 530upx;
			.cate-content {
				width: 100%;
				padding-bottom: 40upx;
			}
      .sec-cate-item{
        padding: 0 30upx;
      }
      .cate-title{
				padding-top: 50upx;
        font-size: 32upx;
        font-weight: 600;
      }
      .third-cate-wrap{
        margin-top:32upx;
         padding: -1upx 19upx;
        .third-cate-item{
          float: left;
          width: 33%;
          text-align: center;
          .product-img{
            width: 104upx;
            height: 100upx;
          }
          .product-name{
            font-size: 24upx;
            color: #666;
            padding-bottom: 20upx;
          }
        }
      }
   }
 }
</style>
