<template>
	<view>
		<view class="list">
			<view class="list_l">
				账号
			</view>
			<view class="list_r">
					<u-input v-model="account" :type="number"  placeholder="请输入账号"/>
			</view>
		</view>
		<view class="list">
			<view class="list_l">
				手机号
			</view>
			<view class="list_r">
					<u-input v-model="phone" :type="number"  placeholder="请输入手机号" @input="getCode"/>
			</view>
		</view>
		<view class="list">
			<view class="list_l">
				验证码
			</view>
			<view class="list_code">
				<u-input v-model="code" :type="number"  placeholder="请输入验证码" style="width: calc(100% - 200rpx);"/>
				<view class="code_btn" v-if="codeShow == false">
					获取验证码
				</view>
				<view class="code_btn" style="opacity: 1;" v-else>
					获取验证码
				</view>
			</view>
		</view>
		<view class="list">
			<view class="list_l">
				输入密码
			</view>
			<view class="list_r">
					<u-input v-model="password" type="password"  placeholder="请输入密码"/>
			</view>
		</view>
		<view class="list">
			<view class="list_l">
				确认密码
			</view>
			<view class="list_r">
					<u-input v-model="password1" type="password"  placeholder="请再次输入密码" @input = 'getQue'/>
			</view>
		</view>
		<view class="btn" v-if="queShow == false">
			确定
		</view>
		<view class="btn" style="opacity: 1;" v-else>
			确定
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				account:'',//账号
				phone:'',//手机号
				code:'',//验证码
				password:'',//密码
				password1:'',//再次设置密码
				codeShow:false,//获取验证码状态
				queShow:false,//获取确认按钮状态
			}
		},
		methods: {
			//获取验证码状态
			getCode() {
				let that = this;
				if(that.phone != '') {
					that.codeShow = true
				}else {
					that.codeShow = false
				}
			},
			//获取确认按钮状态
			getQue() {
				let that = this;
				if(that.password1 != '') {
					that.queShow = true
				}else {
					that.queShow = false
				}
			},
		}
	}
</script>

<style>
	page {
		box-sizing: border-box;
		padding: 0 32rpx;
		padding-top: 176rpx;
	}
	.list {
		width: 100%;
		height: 108rpx;
		border-bottom: 2rpx solid  rgba(235, 237, 240, 0.4);
		display: flex;
		align-items: center;
	}
	.list_l {
		width: 135rpx;
		margin-right: 48rpx;
		color: #323233;
		font-size: 30rpx;
	}
	.list_r {
		width: calc(100% - 183rpx);
	}
	.list_code {
		width: calc(100% - 183rpx);
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.code_btn {
		width: 188rpx;
		height: 64rpx;
		opacity: 0.4;
		background: #ffffff;
		border-radius: 16rpx;
		color: #EB1B34;
		font-size: 28rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.btn {
		margin-top: 64rpx;
		width: 100%;
		height: 88rpx;
		background: #EB1B34;
		border-radius: 88rpx;
		color: #FFFFFF;
		font-size: 32rpx;
		font-weight: 600;
		display: flex;
		align-items: center;
		justify-content: center;
		opacity: 0.4;
	}
</style>
