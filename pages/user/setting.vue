<template>
    <view class="userinfo">
       <u-navbar  title="设置" title-size="28" back-icon-size="28">
       </u-navbar>
       <view class="info">
           <view class="flex flex-justify-between flex-align-center infoItem">
               <view>手机号</view>
               <view class="flex flex-align-center">
                   <view>
                       <u-input v-model="value" type="text" input-align="right"  placeholder="请输入昵称"/>
                   </view>
                   <view><u-icon name="arrow-right"  size="20" color="#D3D3D3"></u-icon></view>
               </view>
           </view>
           <view class="flex flex-justify-between flex-align-center infoItem">
               <view>微信</view>
               <view style="color:red">
                   去绑定<u-icon name="arrow-right"  size="20" color="#D3D3D3"></u-icon>
               </view>
           </view>
           <view class="flex flex-justify-between flex-align-center infoItem">
               <view>密码</view>
               <view><u-icon name="arrow-right"  size="20" color="#D3D3D3"></u-icon></view>
           </view>
           <view class="flex flex-justify-between flex-align-center infoItem">
               <view>投诉建议</view>
               <view><u-icon name="arrow-right"  size="20" color="#D3D3D3"></u-icon></view>
           </view>
       </view>
       <view class="logotBtn">
           <view><view>退出登录</view></view>
       </view>

    </view>
</template>
<script>
export default {
    data(){
        return {
            value:"16728374561",
            
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
    .logotBtn{
        margin:694rpx  194rpx;
    //    height: 88rpx;
       background-color: #D3D3D3;
       color:red;
       border-radius: 20rpx;
       view{
           height: 88rpx;
           display: flex;
           justify-content: center;
           align-items: center;
       }
    }
}
/deep/.u-border-bottom:after{
    border: 0;
}

</style>