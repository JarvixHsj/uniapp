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
                    <view class="sticky flex flex-justify-between tapswiper" >
                            <view v-for="(item,index) in list" :key="index"  :class=" index == 2 || index == 3 ? 'flex' :'' ">
                                {{item}}
                                <view style="width:24rpx;height:24rpx;margin-left:8rpx" v-if="index == 2">
                                    <u-image width="100%" height="100%" src="../../static/image/index/ic_screening_n@3x.png"></u-image>
                                </view>
                                <view style="width:24rpx;height:24rpx;margin-left:8rpx" v-if="index == 3" @click="screening">
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
        <u-popup v-model="sceShow" mode="right" width="90%" border-radius="40">
            <view class="popup-box">
                <view class="hot-search search-box">
                    <view class="search-box-title">一级分类</view>
                    <view class="flex historyData flex-wrap flex-justify-between">
                        <view v-for="item in historyData" :key="item.id" class="historyItem" style="margin:10rpx">
                            {{item.name}}
                        </view>
                    </view>
                </view>
                <view class="hot-search search-box">
                    <view class="search-box-title">二级分类</view>
                    <view class="flex historyData flex-wrap flex-justify-between">
                        <view v-for="item in historyData" :key="item.id" class="historyItem" style="margin:10rpx">
                            {{item.name}}
                        </view>
                    </view>
                </view>
                <view class="hot-search search-box">
                    <view class="search-box-title">价格区间(元)</view>
                    <view class="flex historyData" style="align-items:center">
                        <view><u-search placeholder="最低价" input-align="center" search-icon="" :show-action="false" v-model="key"></u-search></view>
                        <view>-</view>
                        <view><u-search placeholder="最高价" input-align="center"  search-icon=""  :show-action="false" v-model="key"></u-search></view>
                    </view>
                    <view class="flex historyData flex-wrap flex-justify-between">
                        <view  class="historyItem" style="margin:10rpx;color:#323233">
                            只看有库存
                        </view>
                    </view>
                </view>
                <view style="position:fixed;left:0px;bottom:68rpx;width:100%;border-top:1px solid rgba(247,248,250,1);" class="flex">
                    <view style="margin:32rpx 16rpx 32rpx 32rpx; flex:0 0 30%">
                        <u-button shape="circle">重置</u-button>
                    </view>
                    <view style="margin:32rpx 32rpx 32rpx 16rpx;flex:0 0 55%">
                        <u-button shape="circle">确定</u-button>
                    </view>
                </view>
            </view>
            
        </u-popup>     
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
            key:"",
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
            ],
            sceShow:false,
            historyData:[
                {id:1,name:'名创优品'},
                {id:2,name:'名创优品'},
                {id:3,name:'名创优品'},
                {id:4,name:'名创优品'},
                {id:5,name:'名创优品'},
                {id:6,name:'名创优品'}
            ],
        }
    },
    components:{
			GoodItem,
		},
    methods:{
        toSearch(){
            
        },
        screening(){
            this.sceShow = true
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
    .sticky{
        background:#fff;
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
.popup-box{
    margin: 32rpx;
    margin-top:108rpx;
    height: calc(100% - 64rpx);
    .search-box{
        margin: 32rpx;
        .search-box-title{
            font-weight: 500;
        }
        .delbox{
            width: 32rpx;
            height: 32rpx;
        }
        .historyData{
            margin: 34rpx 0rpx;
            .historyItem{
                margin: 10rpx 32rpx 10rpx 0rpx;
                font-size: 24rpx;
                padding: 10rpx 16rpx;
                border-radius: 12px;
                opacity: 1;
                background: rgba(247,248,250,1);
                color: rgba(100,101,102,1)
            }
        }
        
    }
}
</style>
