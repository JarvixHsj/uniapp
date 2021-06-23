<template>
    <view class="search-page">
        <view>
            <u-navbar>
                <view class="slot-wrap"><u-search placeholder="日照香炉生紫烟" v-model="keyword" :show-action="false"></u-search></view>
            </u-navbar>
        </view>
        <view>
            <u-sticky>
			<!-- 只能有一个根元素 -->
                <view class="sticky">
                    <view class="flex flex-justify-between tapswiper" >
                            <view v-for="(item,index) in list" :key="index" >
                                {{item}}
                                <view style="width:24rpx;height:24rpx;margin-left:8rpx" v-if="index == 3">
                                    <u-image width="100%" height="100%" src="../../static/image/index/ic_filter@2x.png"></u-image>
                                </view>
                            <!-- </view> -->
                        </view>
                    </view>
                </view>
            </u-sticky>
             </view>
        <view class="search-result">
                <good-item :goodData="goodData"></good-item> 
        </view>     
    </view>
</template>
<script>
import GoodItem from '../../components/GoodItem'
export default {
    data(){
        return {
            list:[
                "新品","销量","价格","筛选"
            ], 
            keyword:'nike',
            goodData:[
                {
                    image:"Rectangle 2372.png",
                    title:"YSL圣罗兰年春夏 女士 夹克刺绣丝绒",
                    price:"288.90",
                    hadsale:"256",
                    originalPrice:""
                },{
                    image:"Rectangle 2372.png",
                    title:"YSL圣罗兰年春夏 女士 夹克刺绣丝绒",
                    price:"288.90",
                    hadsale:"256",
                    originalPrice:""
                },{
                    image:"Rectangle 2372.png",
                    title:"YSL圣罗兰年春夏 女士 夹克刺绣丝绒",
                    price:"288.90",
                    hadsale:"256",
                    originalPrice:"368.90"
                },{
                    image:"Rectangle 2372.png",
                    title:"YSL圣罗兰年春夏 女士 夹克刺绣丝绒",
                    price:"288.90",
                    hadsale:"256",
                    originalPrice:"368.90"
                },
                {
                    image:"Rectangle 2372.png",
                    title:"YSL圣罗兰年春夏 女士 夹克刺绣丝绒",
                    price:"288.90",
                    hadsale:"256",
                    originalPrice:"368.90"
                },
            ]
        }
    },
    components:{
			GoodItem,
		},
    method:{
        toSearch(){
            
        }
    }
}
</script>
<style lang="scss" scoped>
.search-page{
    background-color: #F2F3F5;
    .slot-wrap {
        display: flex;
        align-items: center;
        flex: 1; 
        padding: 0 30rpx; 
    }
    .tapswiper{
        font-size: 26rpx;
        color:#323233;
        font-weight: 400;
        padding:24rpx 40rpx;
    }
    .search-result{
        margin: 24rpx 32rpx;
    }
     
}
</style>
