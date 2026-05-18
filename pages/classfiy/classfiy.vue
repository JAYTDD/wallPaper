<template>
	<view class="layout pageBg">
		<custom-nav-bar title="分类"></custom-nav-bar>
		<view class="classfiy">
			<theme-item v-for="item in 8"></theme-item>
			<theme-item :isMore="true"></theme-item>
		</view>
	</view>
</template>

<script setup>
	
</script>

<style lang="scss" scoped>
	.layout{	
		.classfiy{
			padding: 0 30rpx;
			padding-top: 30rpx;
			display: grid;
			gap: 15rpx;
			grid-template-columns: repeat(3,1fr);
		}
	}
</style>