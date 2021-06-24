<template>
    <view class="class_item flex">
        <view v-for="(item,index) in classData" :key="index" class="item"> 
            <view class="item_img">
                <u-image width="100%" height="100%" :src="item.src"></u-image>
            </view>
            <view class="item_title">
                {{item.title}}
            </view>
        </view>
    </view>
</template>
<script>
import app from '../App.vue'
export default {
    props:{
        classData:{
            type:Array,
            default:()=>[]
        }
    },
    data(){
        return{
            imageUrl: app.globalData.imageUrl,
            src:'https://cdn.uviewui.com/uview/example/fade.jpg',
        }
    }
}
</script>
<style lang="scss" scoped>
   .class_item{
       flex-wrap: wrap;
    //    justify-content: space-between;
       .item{
        //    text-align: center;
           margin-bottom: 40rpx;
           margin-right: 20rpx;
           margin-left: 20rpx;
          .item_img{
              text-align: center;
              width:76rpx;
              height: 76rpx;
          }
          .item_title{
              color: #323233;
              font-size: 20rpx;
          } 
       }
   }
</style>