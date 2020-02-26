<template>
	<view>
		<view class="sliverRegPage">
			<form @submit="formSubmit" class="sliverReg">
				<view class="uni-form-item uni-column">
					<input class="uni-input" name="username" placeholder="请输入用户名……" />
					<input class="uni-input" password="true" name="userpwd" placeholder="请输入登录密码……" />
					<input class="uni-input" password="true" name="useremail" placeholder="请输入邮箱账号……" />
				</view>
				<view class="uni-btn-v">
					<button formType="submit" type="primary">注册</button>
					<button type="warn">登录</button>
				</view>
			</form>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		},
		methods: {
		//uni-app 提交表单方法
			formSubmit: function(e) {
				//获取表单值
				var formData = e.detail.value;
				// 请求
				uni.request({
					//api地址
					url: 'http://appblog.inacorner.top/wp-content/themes/wpApp/api/reg.php',
					data: {
						//请求值
					     'user_name': formData.username,
						  'user_pwd':formData.userpwd,
						  'user_email:formData.useremail,
					},
					//请求类型
					method:'POST',
					//请求头
					header: {
						'content-type': 'application/x-www-form-urlencoded', 
					},
					success: (res) => {
						console.log(res.data)
						if(res.data.status==2){
							console.log("登录成功！");
						}else{
							console.log(res)
						}
					}
				});
			}
		}
	}
</script>

<style>
	.sliverRegPage {
		padding: 20px 15px;
	}

	.sliverReg uni-input {
		background: #d8d8d8;
		margin-bottom: 1rem;
		padding: 0.5rem;
		font-size: 0.8rem;
		border-radius: 5px;
		color: #424242;
	}

	.sliverReg .uni-btn-v button {
		margin-bottom: .5rem;
	}
</style>
