<template>
	<view class="user-layout pageBg">
		<custom-nav-bar title="我的"></custom-nav-bar>
		<view class="userInfo">
			<view class="avatar">
				<image src="/static/xxmLogo.png" mode=""></image>
			</view>
			<view class="nickname">192.168.1.1</view>
			<view class="address">11111111</view>
		</view>
		
		<view class="section">
			<navigator>
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
			</navigator>
			<navigator>
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
			</navigator>
			<navigator>
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
			</navigator>
		</view>
		
		<view class="section">
			<navigator>
				<view class="list">
					<view class="left">
						<uni-icons type="notification-filled" size="20" color="#28b389"></uni-icons>
						<view class="text">订阅更新</view>
					</view>
					<view class="right">
						<view class="text">111</view>
						<uni-icons type="right" size="15" color="#aaa"></uni-icons>
					</view>
				</view>
			</navigator>
			<navigator>
				<view class="list">
					<view class="left">
						<uni-icons type="help" size="20" color="#28b389"></uni-icons>
						<view class="text">常见问题</view>
					</view>
					<view class="right">
						<view class="text">111</view>
						<uni-icons type="right" size="15" color="#aaa"></uni-icons>
					</view>
				</view>
			</navigator>
		</view>
		
	</view>
</template>

<script setup>
	
</script>

<style lang="scss" scoped>
	.user-layout{	
		padding-top: 250rpx;
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
		width: 690rpx;
		margin: 50rpx auto;
		border: 1px solid #eee;
		border-radius: 10rpx;
		box-shadow: 0 0 30rpx rgba(0, 0, 0, 0.05);
		overflow: hidden;
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
				.text{
					padding-left: 20rpx;
					color: #333;
				}
			}
			.right{
				display: flex;
				align-items: center;
				.text{
					font-size: 28rpx;
					color: #aaa;
					padding-right: 20rpx;
				}
			}
		}
		.list:last-child{
			border-bottom: none;
		}
	}
	navigator{
		display: block;
	}
</style>