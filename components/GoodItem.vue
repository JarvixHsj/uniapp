<template>
    <view class="article_conent">
        <view class="article_conent_list" v-for="(item,index) in goodData" :key="index">
                <view style="width: 334rpx; height: 334rpx;">
                    <u-image width="100%" height="100%"  :src="imageUrl +item.image"></u-image>
                </view>
				
				<view class="article_conent_list_base">
					<view class="article_conent_list_base_t">
						{{item.title}}
					</view>
					<view class="article_conent_list_base_c">
						<text style="color: #FF2F2F;font-size: 24rpx;font-weight: 600;">¥</text>
                        <text style="color: #FF2F2F; font-size: 28rpx; font-weight: 600;">{{item.price}}</text>
                        <text style="color: #C8C9CC; font-size: 22rpx; margin-left: 8rpx;">已售{{item.hadsale}}</text>
					</view>
					<view class="article_conent_list_base_b" v-if="item.originalPrice">
						¥{{item.originalPrice}}
					</view>
				</view>
			</view>
    </view>
</template>
<script>
import app from '../App.vue'
export default {
    props:{
        goodData:{
            type:Array,
            default:()=>[]
        }
    },
    data(){
        return{
            imageUrl: app.globalData.imageUrl,
        }
    }
}
</script>
<style lang="scss" scoped>
    .article_conent_list {
		width: 334rpx;
		// height: 531rpx;
		background: #FFFFFF;
		border-radius: 16rpx;
        margin-bottom: 20rpx;
	}
	.article_conent_list_base {
		width: 100%;
		// height: 198rpx;
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