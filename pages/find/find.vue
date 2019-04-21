<template>
	<view>
		<!-- 教程uni-app渲染发现界面第四步:渲染分类数据 -->
		<view class="catItem page-section">
			<view class="catList" v-for="(item , index) in catsData" :key="index">
				<view>
					{{item.name}}
				</view>
			</view>
		</view>
		<!-- 教程uni-app渲染发现界面第五步:渲染文章数据 -->
		<view class="page-section postBox">
			<view class="postList" v-for="(item , index) in postsData" :key="index">
				<image mode="widthFix" :src="item.img"></image>
				<view class="title">
					{{item.title}}
				</view>
			</view>
		</view>
		<!-- 教程uni-app渲染发现界面第六步:渲染文章数据 -->
		<view class="tagItem page-section">
			<view class="tagList" v-for="(item , index) in tagsData" :key="index">
				<view>
					{{item.name}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tagsData:[],//教程uni-app渲染发现界面第一步定义值接收标签数据
				catsData:[],//教程uni-app渲染发现界面第一步定义值接收分类数据
				postsData:[],//教程uni-app渲染发现界面第一步定义值接收文章数据
			};
		},
		onLoad() {
			//教程uni-app渲染发现界面第三步将请求方法放入onLoad：
			this.getFindData();
		},
		methods: {
			//教程uni-app渲染发现界面第二步定义请求方法
			getFindData(){
				var _self = this;
				var findData = [];
				uni.request({
					url: 'http://appblog.inacorner.top/wp-content/themes/wpApp/api/find.php',//接口地址
					success: (res) => {
						// 请求成功之后将数据赋值给findData,然后通过findData分别将值传给初始定义的几个数组
						findData=res.data;
						_self.catsData = findData.cats;
						_self.postsData = findData.posts;
						_self.tagsData = findData.tags;
					}
				});
			}
			
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
