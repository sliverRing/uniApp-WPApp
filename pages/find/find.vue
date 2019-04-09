<template>
	<view>
		<view class="catItem page-section">
			<view class="catList">分类</view>
			<view class="catList">分类</view>
			<view class="catList">分类</view>
			<view class="catList">分类</view>
			<view class="catList">分类</view>
			<view class="catList">分类</view>
		</view>
		<view class="page-section postBox">
			<view class="postList">
				<image mode="widthFix"></image>
				<view class="title">
					文章标题
				</view>
			</view>
			<view class="postList">
				<image mode="widthFix"></image>
				<view class="title">
					文章标题
				</view>
			</view>
				<view class="postList">
				<image mode="widthFix"></image>
				<view class="title">
					文章标题
				</view>
			</view>
		</view>
		<view class="tagItem page-section">
			<view class="tagList">标签</view>
			<view class="tagList">标签</view>
			<view class="tagList">标签</view>
			<view class="tagList">标签</view>
			<view class="tagList">标签</view>
			<view class="tagList">标签</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style>
.catItem,.tagItem {
    display: flex;
    flex-wrap: wrap;
}
.catList,.tagList {
    flex-grow: 1;
    width: calc(98% / 3);
    text-align: center;
    line-height: 2;
    background-color: #757575;
    color: #cecece;
}
.postBox uni-image {
    width: 100%;
    height: 10rem;
    background: #eaeaea;
	}
.postList .title {
	    background: #000;
	    color: #fff;
	    font-size: 16px;
	    line-height: 37px;
	    padding: 0 10px;
		margin-top: -5px;
	}
.postList{
	margin-bottom: 1rem;
}
.postList:last-child{ 
margin-bottom: 0rem;
}
</style>
