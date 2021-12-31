<template>
	<view class="content">
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
		<view class="list">
			<view></view>
			<view class="" v-for="(i, index) in list" key="index">
				<view class="friends">
						<view class="friends-left">
							<text v-if="i.tip" class="tip">{{i.tip}}</text>
							<image class="friends-left-img" :src="i.img" mode=""></image>
						</view>
						<view class="friends-right">
							<view class="top">
								<view class="name">
									{{i.name || '开发的实力'}}
								</view>
								<view class="time">
									13:43
								</view>
							</view>
							<view class="bottom">
								{{i.text || '撒谎觉得还是看见哈到家啊说的话就仨繁华的世界复活节岛上飞机的逻辑啊'}}
							</view>
						</view>
					</view>
				
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				list: [{
				img: '../../static/2.png',
					tip: '1',
					name: '想吃流氓兔奶糖',
					text: '你不回我你就是渣男'
				},{
					img: '../../static/4.png',
						tip: '3'
				},{
					img: '../../static/5.png',
					name: '馒头春卷煎饼',
					text: '我没有'
				},{
					img: '../../static/6.png',
					text: '收到了饭就仨江东父老圣诞卡大家分开了的撒肌肤'	
				},
				{
					img: '../../static/7.png',
						tip: '11',
						text: '事实上计算机技术阿手机卡升级撒上世界经济大三大四的对对对的撒撒撒问问'
				},
				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.content {
	}
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
	.list {
		margin: 100rpx  0;
		border-bottom: 0 1rpx 0 0 rgba(0, 0, 0, 0.1);
		.friends{
			padding: 0 $uni-spacing-col-base;
			display: flex;
			flex-direction: row;
			width: 100%;
			.friends-left {
				height: 96rpx;
				padding: 16rpx 0;
				position: relative;
				.tip{
					position: absolute;
					top: 6rpx;
					left: 70rpx;
					height: 36rpx;
					min-width: 36rpx;
					z-index: 1;
					background: $uni-color-warning;
					border-radius: 100%;
					font-size: $uni-font-size-sm;
					color: $uni-text-color-inverse;
					text-align: center;
					line-height: 36rpx;
				}
				.friends-left-img{
						width: 96rpx;
						height: 96rpx;
						border-radius:$uni-border-radius-base;
						background-color: $uni-bg-color-grey;
					}
			}
			.friends-right{
				padding-left: 34rpx;
				width: calc(100% - 170rpx);
				.top {
					display: flex;
					padding-top: 10rpx;
					justify-content: space-between;
					.name{
						font-size: 36rpx;
						height: 50rpx;
						font-weight: 400;
						color: rgba(39,40,50,1);
						line-height: 50rpx;
					}
					.time{
						font-size: $uni-font-size-sm;
						line-height: 50rpx;
						color: $uni-text-color-disable;
					}
				}
				.bottom{
					padding-top: 14rpx;
					line-height: 40rpx;
					font-size: $uni-font-size-sm;
					color: $uni-text-color-disable;
					overflow: hidden;
					white-space: nowrap;
					text-overflow: ellipsis;
				}
			}
		}
		.friends:active {
			background-color: #999999;
		}
	}
</style>
