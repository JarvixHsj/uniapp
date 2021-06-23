<template>
    <view class="search-page">
        <view class="search-input"> 
            <u-search :show-action="true" action-text="取消" :animation="false" :action-style="actionStyle" @search="toSearch"></u-search>
        </view>
        <view class="history-search search-box" v-show="isShowHistory">
            <view class="flex flex-justify-between flex-align-center">
                <view class="search-box-title">历史搜索</view>
                <view class="delbox" @click="isShowHistory = false">
                    <u-image width="100%" height="100%" src="../../static/image/index/ic_dele@2x.png"></u-image>
                </view>
            </view>
            <view class="flex historyData flex-wrap">
                <view v-for="item in historyData" :key="item.id" class="historyItem" style="margin:10rpx">
                    {{item.name}}
                </view>
            </view>
        </view>
        <view class="hot-search search-box">
            <view class="search-box-title">热门搜索</view>
            <view class="flex historyData flex-wrap">
                <view v-for="item in historyData" :key="item.id" class="historyItem" style="margin:10rpx">
                    {{item.name}}
                </view>
            </view>
        </view>
    </view>
</template>
<script>
export default {
    data(){
        return {
            historyData:[
                {id:1,name:'名创油瓶'},
                {id:2,name:'名创油瓶'},
                {id:3,name:'YSL圣罗兰年春夏 女士'},
                {id:4,name:'名创油瓶'}
            ],
            isShowHistory:true,
            actionStyle:{'font-weight':500}
        }
    },
    methods:{
        toSearch(){
            uni.navigateTo({
                url:'./searchResult'
            })
        }
    }
}
</script>
<style lang="scss" scoped>
.search-page{
    .search-input{
      margin: 28rpx 24rpx;  
    }
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
