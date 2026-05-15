<template>
	<view class="homelayout">	
		<view class="banner">
			<swiper indicator-dots indicator-active-color= "rgba(255,255,255,0.5)"
				autoplay circular>
				<swiper-item v-for="item in 3">
					<image src="/common/wallpaper/banner1.jpg" mode=""></image>
				</swiper-item>
			</swiper>
		</view>
		
		<view class="notice">
				<view class="left">
					<uni-icons type="sound" size="20" color="#28b389"></uni-icons>
					<text class="text">公告</text>
				</view>
				<view class="center">
					<swiper vertical interval="1500" autoplay duration="300" circular >
						<swiper-item v-for="item in 3">1111111111111111111111111111111111111111111111111111111111111</swiper-item>	
					</swiper>
				</view>
				<view class="right">
					<uni-icons type="right" size="20" color="#28b389"></uni-icons>
				</view>
		</view>
		
		<view class="select">
			<common-title>1111111</common-title>
			<view class="content">
				<scroll-view scroll-x >
					<view class="box" v-for="item in 7">
						<image src="/common/wallpaper/preview2.jpg" mode=""></image>
					</view>
				</scroll-view>
			</view>
		</view>
	</view>
</template>

<script setup>
	
</script>

<style lang="scss" scoped> 
	.homelayout{
		
		.banner{
			padding: 20rpx 0;
			width: 750rpx;
			swiper{
				width: 750rpx;
				height: 340rpx;
				swiper-item{
				padding: 0 30rpx;
					image{
						width: 100%;
						height: 100%;
					}
				}
			}
		}
		.notice{
			width: 690rpx;
			height: 80rpx;
			line-height: 80rpx;
			background-color: #f9f9f9;
			padding: 0 30rpx;
			margin: auto;
			border-radius: 80rpx;
			display: flex;
			.left{
				display: flex;
				justify-content: center;
				width: 120rpx;
				.text{
					color: #28b389;
					font-size: 28rpx;
					font-weight: 600;
				}
			}
			.center{
				height: 100%;
				flex: 1;
				swiper{
					height: 100%;
					swiper-item{
						width: 100%;
						height: 100%;
						font-size: 30rpx;
						color: #666;
						display: block;
						overflow: hidden; //超出部分隐藏起来
						text-overflow: ellipsis; //超出部分省略号
						white-space: nowrap; //不换行
					}
				}
			}
			.right{
				display: flex;
				justify-content: center;
				width: 70rpx;
			}
		}
		.select{
			padding-top: 50rpx;
			.content{
				width: 720rpx;
				margin-top: 30rpx;
				margin-left: 30rpx;
				scroll-view{
					white-space: nowrap;
					.box{
						display: inline-block;
						width: 200rpx;
						height: 430rpx;
						margin-right: 15rpx;
						image{
							width: 100%;
							height: 100%;
						}
					}
					.box:last-child{
						margin-right: 30rpx;
					}
				}
			}
		}
	}
	
</style>