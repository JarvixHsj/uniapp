<template>
	<view>
		<!-- 关闭 -->
		<view class="close">
			<image :src="imageUrl+'ic_login.png'" mode="" style="width: 40rpx; height: 40rpx;" @click="getClose"></image>
		</view>
		<view class="login">
			密码登录
		</view>
		<!-- 表单 -->
		<view class="from">
			<view class="from_phone">
				<u-input v-model="phone" :type="type" style="width: 100%;" placeholder='请输入账号 '
					placeholder-style="color:#c0c4cc;font-size:30rpx;" />
			</view>
			<view class="from_code">
				<u-input v-model="code" :type="type1" placeholder='请输入密码 ' style="width: 100%;" @input="getCodeShow" />
			</view>
			<!-- 忘记密码 -->
			<view class="forget" @click="getForget">
				忘记密码?
			</view>
			<!-- 登录 -->
			<view class="deng" v-if="codeShow == false">
				登录
			</view>
			<view class="deng" style="opacity: 1;" v-else>
				登录
			</view>
			<view class="deng_base">
				<view class="deng_base_l" @click="getCode">
					验证码登录
				</view>
				<view class="deng_base_r" @click="getRegister">
					注册
				</view>
			</view>
		</view>

		<!-- 微信登录 -->
		<view class="wx">
			<image :src="imageUrl+'ic_wechat.png'" mode="" style="width: 96rpx; height: 96rpx;"></image>
		</view>
		<!-- 协议 -->
		<view class="base" @click="getBase">
			<image :src="imageUrl+'ic_circel.png'" mode="" style="width: 36rpx; height: 36rpx;"
				v-if="baseShow == false"></image>
			<image :src="imageUrl+'ic_checked.png'" mode="" style="width: 36rpx; height: 36rpx;" v-else></image>
			<text style="color: #C8C9CC; font-size: 22rpx; margin: 0 16rpx;">我已阅读并同意</text>
			<text style="color: #323233; font-size: 22rpx; margin-right: 16rpx;">用户协议</text>
			<text style="color: #323233; font-size: 22rpx;">隐私政策</text>
		</view>
	</view>
</template>

<script>
	import app from '../../App.vue'
	export default {
		data() {
			return {
				imageUrl: app.globalData.imageUrl,
				phone: '',//账号
				code: '', //密码
				type: 'number',
				type1:'password',
				baseShow: false, //是否阅读协议
				codeShow: false, //验证码按钮状态
				
			}
		},
		methods: {
			//阅读协议
			getBase() {
				let that = this;
				that.baseShow = !that.baseShow;
			},
			//获取登录按钮状态
			getCodeShow() {
				let that = this;
				if (that.phone != '' && that.code !='') {
					that.codeShow = true
				} else {
					that.codeShow = false
				}
			},
			//关闭
			getClose() {
				let that = this;
				uni.switchTab({
					url:'../index/index'
				})
			},
			//前往验证码页面
			getCode() {
				uni.redirectTo({
					url:'./login'
				})
			},
			//前往忘记密码页面
			getForget() {
				uni.navigateTo({
					url:'./forget'
				})
			},
			//前往注册页面
			getRegister() {
				uni.navigateTo({
					url:'./register'
				})
			}
		}
	}
</script>

<style>
	.close {
		width: 100%;
		margin-top: 108rpx;
		box-sizing: border-box;
		padding: 0 36rpx;
		display: flex;
		align-items: center;
		justify-content: flex-start;
	}

	.login {
		margin-top: 100rpx;
		width: 100%;
		color: #323233;
		font-size: 40rpx;
		font-weight: 700;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.from {
		margin-top: 128rpx;
		width: 100%;
		box-sizing: border-box;
		padding: 0 80rpx;
	}

	.from_phone {
		width: 100%;
		height: 108rpx;
		display: flex;
		align-items: center;
		border-bottom: 2rpx solid rgba(235, 237, 240, 0.4);
	}

	.from_code {
		margin-top: 24rpx;
		width: 100%;
		height: 108rpx;
		display: flex;
		align-items: center;
		border-bottom: 2rpx solid rgba(235, 237, 240, 0.4);
	}

	.from_code_btn {
		width: 188rpx;
		height: 64rpx;
		opacity: 0.4;
		background: #ffffff;
		border-radius: 16rpx;
		color: #EE0A24;
		font-size: 28rpx;
		font-weight: 700;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.deng {
		margin-top: 62rpx;
		width: 590rpx;
		height: 88rpx;
		opacity: 1;
		background: #eb1b34;
		border-radius: 88rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		color: #FFFFFF;
		font-size: 32rpx;
		font-weight: 600;
		opacity: 0.4;
	}

	.deng_base {
		width: 100%;
		margin-top: 32rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
		color: #323233;
	}

	.deng_base_l {
		font-size: 26rpx;
	}

	.deng_base_r {
		font-size: 24rpx;
	}

	.wx {
		position: fixed;
		left: 50%;
		transform: translateX(-50%);
		bottom: 180rpx;
	}

	.base {
		position: fixed;
		left: 0;
		right: 0;
		bottom: 82rpx;
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.forget {
		margin-top: 32rpx;
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		color: #969799;
		font-size: 24rpx;
	}
</style>
