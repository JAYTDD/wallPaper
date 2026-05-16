<template>
	<view class="user-layout pageBg">
		<view class="userInfo">
			<view class="avatar">
				<image src="/static/xxmLogo.png" mode=""></image>
			</view>
			<view class="nickname">192.168.1.1</view>
			<view class="address">11111111</view>
		</view>
		
		<view class="section">
			<view class="list">
				<view class="left">
					<uni-icons type="download-filled" size="20" color="#28b389"></uni-icons>
					<view class="text">我的下载</view>
				</view>
				<view class="right">
					<view class="text">111</view>
					<uni-icons type="right" size="15" color="#aaa"></uni-icons>
				</view>
			</view>
			<view class="list">
				<view class="left">
					<uni-icons type="star-filled" size="20" color="#28b389"></uni-icons>
					<view class="text">我的评分</view>
				</view>
				<view class="right">
					<view class="text">111</view>
					<uni-icons type="right" size="15" color="#aaa"></uni-icons>
				</view>
			</view>
			<view class="list">
				<view class="left">
					<uni-icons type="chat" size="20" color="#28b389"></uni-icons>
					<view class="text">联系客服</view>
				</view>
				<view class="right">
					<view class="text">111</view>
					<uni-icons type="right" size="15" color="#aaa"></uni-icons>
				</view>
			</view>
			<!-- #ifdef H5 -->
				<button>拨打电话</button>
			<!-- #endif -->
			<!-- #ifdef MP-WEIXIN -->
				<button open-type="contact">联系客服</button>
			<!-- #endif -->
			
		</view>
		
		<view class="section">
			<view class="list">
				<view class="left">
					<uni-icons type="notification" size="20" color="#28b389"></uni-icons>
					<view class="text">订阅更新</view>
				</view>
				<view class="right">
					<view class="text">111</view>
					<uni-icons type="right" size="15" color="#aaa"></uni-icons>
				</view>
			</view>
			<view class="list">
				<view class="left">
					<uni-icons type="flag" size="20" color="#28b389"></uni-icons>
					<view class="text">常见问题</view>
				</view>
				<view class="right">
					<view class="text">111</view>
					<uni-icons type="right" size="15" color="#aaa"></uni-icons>
				</view>
			</view>
		</view>
		
		
	</view>
</template>

<script setup>
	
</script>

<style lang="scss" scoped>
	.user-layout{	
		
		.userInfo{
			display: flex;
			align-items: center;
			justify-content: center;
			flex-direction: column;
			.avatar{
				width: 160rpx;
				height: 160rpx;
				border-radius: 50%;
				overflow: hidden;
				image{
					width: 100%;
					height: 100%;
				}
			}
			.nickname{
				font-size: 44rpx;
				color: #333;
				padding: 20rpx 0 5rpx;
			}
			.address{
				font-size: 28rpx;
				color: #aaa;
			}
		}
	}
	.section{
		position: relative;
		width: 690rpx;
		margin: 50rpx auto;
		border: 1px solid #eee;
		border-radius: 10rpx;
		box-shadow: 0 0 30rpx rgba(0, 0, 0, 0.05);
		.list{
			background-color: white;
			padding: 25rpx 10rpx;
			display: flex;
			align-items: center;
			justify-content: space-between;
			border-bottom: 1rpx solid #eee;
			.left{
				display: flex;
				align-items: center;
				justify-content: center;
				.text{
					padding: 20rpx 0;
					padding-left: 20rpx;
				}
			}
			.right{
				display: flex;
				align-items: center;
				justify-content: center;
				.text{
					font-size: 28rpx;
					color: #aaa;
					padding-right : 20rpx;
				}
			}
			
		}
		button{
			height: 135rpx;
			opacity: 0;
			position: absolute;
			left: 0;
			top: 265rpx;
			width: 690rpx;
		}
	}
		
</style>