<script>
export default {
	onLaunch: function() {
		console.log('App Launch');
	},
	onShow: function() {
		console.log('App Show');
	},
	onHide: function() {
		console.log('App Hide');
	}
};
</script>

<style>
/*每个页面公共css */
page {
	background: #f5f5f5;
	color: #333333;
}
/* 教程《用uni-app制作首页文章列表》首页文章列表css代码 */
.indexList uni-image,.postList  image{
	width: 100%;
	height: 270rpx;
	background: #eaeaea;
	border-radius: 15rpx;
}
.indexList,.postList {
	margin-bottom: 15rpx;
	padding: 20rpx 15rpx;
	background-color: #fff;
}
.indexList .title,.postList .title {
	font-size: 16rpx;
	line-height: 37px;
	padding: 0 10px;
	margin-top: -5px;
}
.indexListBox {
	margin-top: 20px;
}
uni-button{
	border-radius: 0;
}
uni-button[type=primary] {
    color: #fff;
    background-color: #795647;
}
uni-button[type=warn] {
    color: #fff;
    background-color: #607D8B;
}
.button-hover[type=primary] {
    background-color: #795647ab;
    border: 0;
}
.button-hover[type=warn] {
    background-color: #607d8bba;
}
</style>
