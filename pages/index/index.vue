<template>
	<view>
		<view class="uni-padding-wrap">
			<view class="page-section swiper">
				<view class="page-section-spacing">
					<!-- 一组幻灯片代码开始，用到组件swiper -->
					<!-- indicator-dots autoplay interval……：组件相关属性，具体可以查看官网说明 -->
					<swiper class="swiper" 
					indicator-dots="indicatorDots" 
					autoplay="autoplay" 
					interval="interval" 
					duration="duration"
					>
					<!-- 教程uni-app渲染幻灯片数据第三步：渲染数据 -->
						<swiper-item v-for="(item , index) in homeSlide" :key="index">
							<!-- uni img组件 src绑定值为服务端返回的数据中的文章缩略图 -->			
							<image :src="item.img" mode="center"></image>
						</swiper-item>
					</swiper>
				</view>
			</view>
			<!-- 教程《用uni-app制作首页文章列表》首页文章列表模板代码 -->
			<view class="page-section indexListBox">
				<!-- 教程 uni-app:渲染app的首页文章数据第四步:绑定渲染数据 -->
				<view class="indexList" v-for="(item , index) in homePosts" :key="index">
					<image :src="item.img" mode="center"></image>
					<view class="title">
						{{item.title}}
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		//此处为该页面需要用到的数据，在项目逻辑中可以对这些数据进行改变
		data() {
			return {
				homeSlide: [] ,//教程uni-app渲染幻灯片数据第一步：定义值接收幻灯片数据
				homePosts:[],//教程 uni-app:渲染app的首页文章数据第一步:定义一个值来接收文章列表
			}
		},
		onLoad() {
			//教程uni-app渲染幻灯片数据第三步：执行方法getHomeSlide（）
			this.getHomeSlideFunc();
			//教程 uni-app:渲染app的首页文章数据第一步:将该方法加入onLoad中，使页面一加载的时候就获取文章列表
			this.getHomePosts();
		},
		//此处为自定义方法
		methods: {
			//教程uni-app渲染幻灯片数据第二步：定义获取幻灯片数据的方法getHomeSlide（）
			getHomeSlideFunc() {
				var _self = this;
				// 用uniapp的request发起请求
				uni.request({
					url: 'http://appblog.inacorner.top/wp-content/themes/wpApp/api/homeSlide.php',//接口地址
					success: (res) => {
						// 请求成功之后将幻灯片数据赋值给homeSlide
						_self.homeSlide=res.data.post;
					}
				});
			},
			// 教程 uni-app:渲染app的首页文章数据第一步:定义方法获取首页文章列表接口getHomePosts（）
			getHomePosts(){
				var _self = this;
				uni.request({
					url: 'http://appblog.inacorner.top/wp-content/themes/wpApp/api/indexList.php',//接口地址
					success: (res) => {
						// 请求成功之后将文章列表数据赋值给homePosts
						_self.homePosts=res.data.post;
					}
				});
			}
		}
	}
</script>

<style>
	.page-section.swiper{
		background-color: #FFFFFF;
		padding: 20rpx;
	}
	/* 将这组幻灯片中的子项目改成我们设计图中的灰色 */
	swiper-item {
		overflow: hidden;
		height: 270rpx;
	}
	/* 教程uni-app渲染幻灯片数据最后一步：美化 */
	swiper-item image{
		height: 100%;;
		width: 100%;
		border-radius: 15rpx;
	}
</style>
