<template>
    <view class="userinfo">
       <u-navbar  title="个人信息" title-size="28" back-icon-size="28">
           <view class="navbarRight" slot="right">保存</view>
       </u-navbar>
       <view class="info">
           <view class="flex flex-justify-between flex-align-center infoItem">
               <view>头像</view>
               <view class="flex flex-align-center">
                   <view>
                       <u-image width="88rpx" height="88rpx" shape="circle" src="../../static/image/ic_wechat.png"></u-image>
                   </view>
                   <view><u-icon name="arrow-right"  size="32" color="#D3D3D3"></u-icon></view>
               </view>
           </view>
           <view class="flex flex-justify-between flex-align-center infoItem">
               <view>账号</view>
               <view><u-input v-model="value" type="text" input-align="right"  placeholder="请输入昵称"/></view>
           </view>
           <view class="flex flex-justify-between flex-align-center infoItem">
               <view>昵称</view>
               <view><u-input v-model="value1" type="text" input-align="right"  placeholder="请输入昵称"/></view>
           </view>
       </view>
    </view>
</template>
<script>
export default {
    data(){
        return {
            value:"KKSD981",
            value1:""
            
        }
    }
}
</script>
<style scoped lang="scss">
.userinfo{
    .navbarRight{
        margin: 20rpx;
    }
    .info{
        .infoItem{
            margin: 48rpx 32rpx;
        }
    }

}
/deep/.u-border-bottom:after{
    border: 0;
}
</style>