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
							<image :src="item.img" mode=""></image>
						</swiper-item>
					</swiper>
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
				homeSlide: [] //教程uni-app渲染幻灯片数据第一步：定义值接收幻灯片数据
			}
		},
		onLoad() {
			
			//教程uni-app渲染幻灯片数据第三步：执行方法getHomeSlide（）
			this.getHomeSlideFunc();
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
			}
		}
	}
</script>

<style>
	/* 将这组幻灯片中的子项目改成我们设计图中的灰色 */
	swiper-item {
		background-color: #f8f8f8;
	}
	/* 教程uni-app渲染幻灯片数据最后一步：美化 */
	swiper-item image{
		width: 100%;
	}
</style>
