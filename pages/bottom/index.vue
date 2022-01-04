<template>
	<view class="">
		<view class="top-bar">
			<view class="top-bar-left">
				<image class="top-bar-left-img" src="../../static/guan.gif" mode=""></image>
			</view>
			<view class="top-bar-middle">
				<image class="top-bar-middle-img" src="../../static/3.png" mode=""></image>
			</view>
			<view class="top-bar-right">
				<image class="top-bar-right-img" src="../../static/new_file.svg" mode=""></image>
				<image class="top-bar-right-img" src="../../static/add.svg" mode=""></image>
			</view>
		</view>
		<home :cur="PageCur" v-if="PageCur=='home'" :key="commponent1Key"></home>
		<view class="cu-bar tabbar bg-white shadow foot">
			<view :class="PageCur=='home'?'action text-green':'action text-gray'" @click="NavChange" data-cur="home">
				<view class='cuIcon-homefill'></view>主页
			</view>
			<view :class="PageCur=='peoplelis'?'action text-green':'action text-gray'" @click="NavChange" data-cur="peoplelis">
				<view class='cuIcon-peoplelist'></view>审批
			</view>
			<view :class="PageCur=='profile'?'action text-green':'action text-gray'" @click="NavChange" data-cur="profile">
				<view class='cuIcon-profile'></view>发起
			</view>
			<view :class="PageCur=='people'?'action text-green':'action text-gray'" @click="NavChange" data-cur="people">
				<view class='cuIcon-people'></view>个人
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				PageCur: 'home',
				commponent1Key: 0,
				commponent2Key: 0,
			}
		},
		methods: {
			NavChange: function(e) {
				console.log(e.currentTarget.dataset.cur)
				this.PageCur = e.currentTarget.dataset.cur
			}
		}
	}
</script>

<style lang="scss" scoped>
	.top-bar {
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
		justify-content: space-between;
		box-shadow: 0 1rpx 0 0 rgba(0, 0, 0, 0.1);
		.top-bar-left{
			padding-left: $uni-spacing-col-base;
			padding-top: 10rpx;
			padding-right: 40rpx;
			.top-bar-left-img{
				width: 68rpx;
				height: 68rpx;
				border-radius: 16rpx;
			}
		}
		.top-bar-middle{
			.top-bar-middle-img{
				width: 88rpx;
				height: 42rpx;
			}
		}
		.top-bar-right{
			.top-bar-right-img{
				width: 52rpx;
				height: 52rpx;
				padding-right: 10rpx;
			}
		}
	}
	
</style>
