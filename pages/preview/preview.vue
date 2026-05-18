<template>
	<view class="preview">
		<swiper circular @click="maskchange()">
			<swiper-item v-for="item in 7">
				<image src="/common/wallpaper/preview1.jpg" mode="aspectFill"></image>
			</swiper-item>
		</swiper>
		<view class="mask" v-if="maskState">
			<view class="goback commonstyle" @click="goBack">
				<uni-icons type="back" color="#fff" size="20" :style="{top:getStatusBarHeight() + 'px'}"></uni-icons>
			</view>
			<view class="count commonstyle">3 / 9</view>
			<view class="time commonstyle">16:12</view>
			<view class="date commonstyle">03月18日</view>
			<view class="footer commonstyle">
				<view class="box" @click="infoOpen">
					<uni-icons type="info" size="28"></uni-icons>
					<view class="text">信息</view>
				</view>
				<view class="box" @click="starInfoOpen">
					<uni-icons type="star" size="28"></uni-icons>
					<view class="text">7分</view>
				</view>
				<view class="box">
					<uni-icons type="download" size="28"></uni-icons>
					<view class="text">下载</view>
				</view>
			</view>
		</view>
		
		<uni-popup ref="infoPopup">
			<view class="infoPopup">
				<view class="popHeader">
					<view class=""></view>
					<view class="title">壁纸信息</view>
					<view class="close" >
						<uni-icons @click="infoClose" type="closeempty" size="18"color="#999"></uni-icons>
					</view>
				</view>
				<scroll-view scroll-y>
					<view class="content">
						<view class="row">
							<view class="label">壁纸ID：</view>
							<text selectable class="value">1111111111</text>
						</view>
						<view class="row">
							<view class="label">发布者：</view>
							<text class="value">111</text>
						</view>

						<view class="row">
							<text class="label">评分：</text>
							<view class="value rotebox">
								<uni-rate readonly touchable size="16" />
								<text class="score">10分</text>
							</view>
						</view>

						<view class="row" >
							<text class="label">摘要：</text>
							<view class="value">
								11111111
							</view>
						</view>

						<view class="row">
							<text class="label">标签：</text>
							<view class="value tabs">
								<view class="tab">1111</view>
							</view>
						</view>

						<view class="copyright">
							声明：本图片来用户投稿，非商业使用，用于免费学习交流，如侵犯了您的权益，您可以拷贝壁纸ID举报至平台，邮箱513894357@qq.com，管理将删除侵权壁纸，维护您的权益。
						</view>
					</view>
				</scroll-view>
			</view>
		</uni-popup>
		
		<uni-popup ref="starPopup">
			<view class="starPopup">
				<view class="popHeader">
					<view class="title">评分</view>
					<view class="close" >
						<uni-icons @click="starInfoClose" type="closeempty" size="20"color="#999"></uni-icons>
					</view>
				</view>
				<view class="content">
					<uni-rate touchable size="34" allowHalf />
					<text class="score">10分</text>
				</view>
				<view class="footer"> 
						<button>确认评分</button>
				</view>
			</view>
		</uni-popup>
	</view>
</template>

<script setup>
import { ref } from 'vue';
import { getStatusBarHeight } from '@/utils/system.js';
	const maskState = ref(true)
	const infoPopup = ref(null)
	const starPopup = ref(null)
	const goBack = () => {
		uni.navigateBack()
	}
	const maskchange = () => {
		maskState.value = !maskState.value
	}
	
	const infoOpen = () => {
		infoPopup.value.open("bottom")
	}
	const infoClose = () => {
		infoPopup.value.close()
	}
	const starInfoOpen = () => {
		starPopup.value.open("center")
	}
	const starInfoClose = () => {
		starPopup.value.close()
	}
</script>

<style lang="scss" scoped>
	.preview{
		position: relative;
		width: 100%;
		height: 100vh;
		swiper{
			width: 100%;
			height: 100%;
			image{
				width: 100%;
				height: 100%;
			}
		}
		.mask{	
			.commonstyle{
				left: 0;
				position: absolute;
				margin: auto;
				right: 0;
				color: #fff;
				width: fit-content;
			}
			.goback{
				width:38px;
				height: 38px;
				background: rgba(0,0, 0.5);
				left: 30rpx;
				margin-left: 0;
				border-radius: 40rpx;
				top: 40rpx;
				backdrop-filter: blur(10rpx);
				border:1rpx solid rgba(255,255,255,0.3);
				display: flex;
				align-items: center;
				justify-content: center;
			}
			.count{
				top: 10vh;
				background-color: rgba(0, 0, 0, 0.3);
				font-size: 28rpx;
				border-radius: 40rpx;
				padding: 8rpx 28rpx;
				backdrop-filter: blur(10rpx);
			}
			.time{
				font-size: 140rpx;				
				top: calc(10vh + 80rpx);
				line-height: 1em;
				text-shadow: 0 4rpx rgba(0, 0, 0,0.3);
			}
			.date{
				font-size: 34rpx;
				top: calc(10vh + 220rpx);
				text-shadow: 0 2rpx rgba(0, 0, 0,0.3);
			}
			.footer{
				bottom: 10vh;
				display: flex;
				justify-content: space-around;
				align-items: center;
				width: 65vw;
				border-radius: 120rpx;
				background: rgba(255, 255, 255, 0.8);
				color: black;
				box-shadow: 0 2rpx rgba(0, 0, 0,0.1);
				backdrop-filter: blur(10rpx);
				padding: 2rpx 12rpx;
				.box{
					display: flex;
					flex-direction: column;
					justify-content: center;
					align-items: center;
					.text{
						color: $text-font-color-2;
					}
				}
			}
		}
		
		.infoPopup{
			background-color: #fff;
			padding: 10rpx 30rpx;
			border-radius: 30rpx 30rpx 0 0;
			overflow: hidden;
			.popHeader{
				display: flex;
				justify-content: space-between;
				align-items: center;
			}
			scroll-view{
				max-height: 60vh;
				.content{
					.row{
						display: flex;
						padding: 16rpx 0;
						font-size: 33rpx;
						line-height: 1.7em;
						.label{
							color: $text-font-color-3;
							width: 150rpx;
							text-align: left;
							font-size: 30rpx;
						}
						.value{
							flex: 1;
						}
						.rotebox{
							display: flex;
							align-items: center;
							.score{
								padding-left:20rpx;
							}
						}
						.tabs{
							display: flex;
							flex-wrap: wrap;
							.tab{
								border: 1px solid $brand-theme-color;
								color: $brand-theme-color;
								font-size: 22rpx;
								padding: 10rpx 30rpx;
								border-radius: 40rpx;
								line-height: 1em;
								margin: 0 10rpx 10rpx 0;
							}
						}
					}
				}
			}
		}
		
		.starPopup{
			background-color: #fff;
			width: 70vw;
			height: 20vh;
			border-radius: 30rpx;
			.popHeader{
				.title{
					font-size: 38rpx;
				}	
				display: flex;
				justify-content: space-between;
				align-items: center;
				padding: 20rpx;
			}
			.content{
				display: flex;
				align-items: center;
				justify-content: center;
				.score{
					padding-left: 20rpx;
				}
			}
			.footer{
				padding-top: 40rpx;
				display: flex;
				align-items: center;
				justify-content: center;
			}
			
		}
		
	}
	
</style>