<template>
	<view class="themeItem">
		<navigator url="/pages/classfiy-list/classfiy-list" class="box" v-if="!isMore">
			<image class="pic" src="/common/wallpaper/classify1.jpg" mode=""></image>
			<view class="mask">明星美女</view>
			<view class="tab">3天前更新</view>
		</navigator>
		
		<navigator url="/pages/classfiy/classfiy" open-type="reLaunch" class="box more" v-if="isMore">
			<image class="pic" src="/common/wallpaper/classify1.jpg" mode=""></image>
			<view class="mask">
				<uni-icons type="more" size="34" color="#fff"></uni-icons>
				<view class="text"> 更多 </view>
			</view>
		</navigator>
		
	</view>
</template>

<script setup>
	defineProps({
		isMore: {
			type: Boolean,
			default:false
		}
	})
</script>

<style lang="scss" scoped>
	.themeItem{
		.box{
			position: relative;
			height: 340rpx;
			border-radius: 10rpx;
			overflow: hidden;
			.pic{
				width: 100%;
				height: 100%;
			}
			.mask{
				width: 100%;
				height: 70rpx;
				display: flex;
				justify-content: center;
				align-items: center;
				color: #fff;
				position: absolute;
				bottom: 0;
				left: 0;
				background: rgba(0, 0, 0, 0.2);
				backdrop-filter: blur(20rpx);
				font-weight: 600rpx;
			}
			.tab{
				font-size: 20rpx;
				color: #fff;
				background: rgba(250, 129, 90, 0.7);
				backdrop-filter: blur(20rpx);
				position: absolute;
				top: 0;
				left: 0;
				padding: 6rpx 10rpx;
				border-radius: 0 0 20rpx 0;
				transform: scale(0.9);
				transform-origin: top left;
			}
		}
		.box.more{
			.mask{
				width: 100%;
				height: 100%;
				flex-direction: column;
				.text{
					
				}
			}
		}
	}
</style>