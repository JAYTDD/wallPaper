<template>
	<view class="classlist">
		<view class="content">
			<navigator url="" class="item" v-for="item in 7">
				<image src="/common/design/preview1.jpg" mode="aspectFill"></image>
			</navigator>
		</view>
	</view>
</template>

<script setup>
	
</script>

<style lang="scss" scoped>
	.classlist{
		.content{
			padding: 5rpx;
			display: grid;
			grid-template-columns: repeat(3,1fr);
			gap: 5rpx;
			.item{
				height: 440rpx;
				image{
					display: block;
					width: 100%;
					height: 100%;
				}
			}
		}
	}
</style>