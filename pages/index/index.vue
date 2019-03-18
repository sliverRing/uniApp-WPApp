<template>
    <view>
        <view class="uni-padding-wrap">
            <view class="page-section swiper">
                <view class="page-section-spacing">
				    <!-- 一组幻灯片代码开始，用到组件swiper -->
					<!-- indicator-dots autoplay interval……：组件相关属性，具体可以查看官网说明 -->
                    <swiper class="swiper" indicator-dots="indicatorDots" autoplay="autoplay" interval="interval" duration="duration">
                        <!-- 每组幻灯片中的子项目 1 -->
						<swiper-item>
							<!-- 此处放内容，可以是图片，也可是图片加文字 -->
                        </swiper-item>
						 <!-- 每组幻灯片中的子项目 2 -->
                        <swiper-item>
							<!-- 此处放内容，可以是图片，也可是图片加文字 -->
                        </swiper-item>
						 <!-- 每组幻灯片中的子项目 3 -->
                        <swiper-item>
							<!-- 此处放内容，可以是图片，也可是图片加文字 -->
                        </swiper-item>
                    </swiper>
                </view>
            </view>
        </view>
    </view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	/* 将这组幻灯片中的子项目改成我们设计图中的灰色 */
	swiper-item{
		background-color: #f8f8f8;
	}
</style>
