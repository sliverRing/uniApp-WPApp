<template>
	<view class="userPage">
		<view class="userHeader">
			<text class="userName">{{userData.user_name}}</text>
			<view class="userInfo">
				<text class="regdate">注册时间：{{userData.user_registered}}</text> | 
				<text class="email">邮箱：{{userData.user_email}}</text>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			userData:null//定义接收用户信息的变量https://www.clearnull.com/982.html
		};
	},
	//uni生命周期函数，页面显示就执行，这意味着如果一打开这个页面，如果没登录将永远跳转到登录页面
	onShow() {
		/****************************************************用户是否登录代码开始:https://www.clearnull.com/963.html*****/
		var the = this;
		//uni获取本地数据API
		uni.getStorage({
			key: 'token', //数据key值，也就是你存储数据时的名称
			success: function(res) {
				//数据成功获取，用户已登录，此刻我们再获取用户信息：https://www.clearnull.com/982.html
				uni.getStorage({
					key: 'user', 
					success: function(res) {
						//数据成功获取
						the.userData = res.data;
					},
					fail: function(res) {
						//数据未获取成功，等同于用户没有登录，这里我们直接跳转到登录页面
						uni.navigateTo({
							url: '../login/login',
						});
					}
				});
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

<style>
	.userHeader {
	    background: #fff;
		padding: 30rpx;
	}
	.userHeader .userName{
		color: #795647;
		font-weight: bold;
		letter-spacing: 2rpx;
	}
	.userHeader .userInfo{
		margin-top: 20rpx;
		font-size: 12rpx;
	}
</style>
