<template>
	<view>
		<view class="sliverLoginPage">
            <form @submit="formSubmit" class="sliverLogin">
                <view class="uni-form-item uni-column">
                    <input class="uni-input" name="username" placeholder="请输入用户名……" />
					 <input class="uni-input" password="true" name="userpwd" placeholder="请输入登录密码……" />
                </view>
                <view class="uni-btn-v">
                    <button formType="submit" type="primary" >登录</button>
					<button type="warn">注册</button>
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
		}
	}
</script>

<style>
.sliverLoginPage {
    padding: 20px 15px;
}
.sliverLogin uni-input {
    background: #d8d8d8;
    margin-bottom: 1rem;
    padding: 0.5rem;
    font-size: 0.8rem;
    border-radius: 5px;
	color: #424242;
}
.sliverLogin .uni-btn-v button{
	margin-bottom: .5rem;
}
</style>
