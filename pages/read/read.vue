<template>
	<view>
		<view class="readPage">
			<view class="title">文章标题</view>
			<view class="info">
				<text class="name">作者</text>
				<text class="dot"></text>
				<text class="date">时间</text>
			</view>
			<view class="text">文章内容</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	methods: {}
};
</script>

<style>
	.readPage{
		padding: 30rpx;
		background-color: #FFFFFF;
	}
	.readPage .title{
		letter-spacing: 4rpx;
		border-bottom: 4rpx solid #795647;
		padding-bottom: 10rpx;
		font-weight: bold;
		line-height: 2;
	}
	.readPage .info{
		margin-top: 30rpx;
		font-size: 12rpx;
		display: flex;
		align-items: center;
	}
	.readPage .info .dot{
		display: inline-block;
		width: 10rpx;
		height: 10rpx;
		background-color: #795647;
		border-radius: 10rpx;
		margin: 0 30rpx;
	}
	.readPage .text{
		padding-top: 30rpx;
		margin-top: 30rpx;
		font-size: 28rpx;
		border-top: 4rpx solid #795647;
	}
</style>
