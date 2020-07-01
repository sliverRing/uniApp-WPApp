<template>
	<view></view>
</template>

<script>
export default {
	data() {
		return {};
	},
	//uni生命周期函数，页面显示就执行，这意味着如果一打开这个页面，如果没登录将永远跳转到登录页面
	onShow() {
		/****************************************************用户是否登录代码开始:https://www.clearnull.com/963.html*****/
		//uni获取本地数据API
		uni.getStorage({
			key: 'token', //数据key值，也就是你存储数据时的名称
			success: function(res) {
				//数据成功获取，用户已登录
				console.log(res.data);
			},
			fail: function(res) {
				//数据未获取成功，用户没有登录，这里我们直接跳转到登录页面
				uni.navigateTo({
					url: '../login/login',
				});
			}
		});
		/*************************************用户是否登录代码结束**********************/
	}
};
</script>

<style></style>
