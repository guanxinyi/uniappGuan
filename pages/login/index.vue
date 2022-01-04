<template>
	<view class="">
		<view class="reglist">
			<view class="reglisttext">
				注册
			</view>
		</view>
		<view class="imggxy">
			<image src="../../static/1.jpg" mode=""></image>
		</view>
		<view class="">
			<view class="">
				登录
			</view>
			<view class="">
				您好，欢迎来到guanxiaoxin
			</view>
		</view>
		<view class="inputview">
			<input class="inputxqq" type="text" v-model="name" placeholder="请输入密码"></input>
			<input class="inputxqq" type="password" v-model="password" placeholder="请输入密码"></input>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				name: 'iiii',
				password: '11111'
			}
		}
	}
</script>

<style lang="scss" scoped>
	.reglist{
		height: 88rpx;
		position: fixed;
		display: flex;
		top: 0;
		width: 100%;
		z-index: 1001;
		background: $uni-bg-color;
		flex-direction: row;
		align-items: center;
		padding-top: var(--status-bar-height);
		justify-content: flex-end;
		.reglisttext{
			width: 72rpx;
			height: 50rpx;
			font-size: 36rpx;
			color: #333333;
			letter-spacing: 0;
			font-weight: 500;
			margin-right: 40rpx;
		}
		
	}
	.inputview {
		margin-left: 60rpx;
		.inputxqq {
			border-bottom: 1rpx solid rgba(0, 0, 0, 0.1);
			height: 100%;
			padding: $uni-spacing-col-lg $uni-spacing-row-lg;
		}	
	}
	.imggxy{
		padding: 120rpx
	}
</style>
