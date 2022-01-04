<template>
	<view class="content">
		<view class="list">
			<view></view>
			<view class="isFirends" v-for="(i, index) in list" key="index">
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
				list: []
			}
		},
		created() {
			// console.log(data[1].data)
			// this.list = data[1].data;
		},
		onLoad() {

		},
		methods: {
			get() {
				uni.request({
								url: "http://192.168.10.115:3000/mail",
								data:{
									email: '1191548004@qq.com'
								},
								method: 'POST',
							})
			}
		}
	}
</script>

<style lang="scss" scoped>
	
	.list {
		padding: 100rpx  0;
		.isFirends{
			border-bottom:1rpx solid rgba(0, 0, 0, 0.1);
		}
		.friends{
			padding: 0 $uni-spacing-col-base $uni-spacing-col-base;
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
				width: calc(100% - 110rpx);
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
