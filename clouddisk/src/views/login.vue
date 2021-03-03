<template>
	<div class="login-wrapper d-flex  justify-content-center">
		<div class=" bg-white login-header rounded p-3 pt-3">
			<div class="mb-4 d-flex flex-column align-items-center justify-content-center">
				<div class="d-flex align-items-center">
					<Icon type="md-briefcase" size="55" color="#2db7f5" />
					<h3 class="text-muted ml-2">企业网盘</h3>
				</div>
				<span class="text-muted small mt-3">企业级网盘解决方案</span>
			</div>
			<Form ref="formItem" :label-width="0" :model="formItem" :rules="rules">
				<FormItem prop="username">
					<Input v-model="formItem.username" placeholder="请输入用户名..."></Input>
				</FormItem>
				<FormItem prop="password">
					<Input type="password" v-model="formItem.password" placeholder="请输入密码..."></Input>
				</FormItem>
				<div class="d-flex align-items-center mb-2">
					<Checkbox v-model="formItem.remember">自动登录</Checkbox>
					<a href="#" class="ml-auto small">忘记密码?</a>
					<span class="mx-1">|</span>
					<a href="#" class="small">注册账户</a>
				</div>
				<FormItem>
					<Button type="primary" long  @click="handleSubmit('formItem')">登录</Button>
				</FormItem>
			</Form>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				formItem: {
					username: "",
					password: "",
					remember: false
				},
				rules: {
					username: [{
						required: true,
						message: '请输入用户名...',
						trigger: 'blur'
					}],
					password: [{
							required: true,
							message: '请输入密码...',
							trigger: 'blur'
						},
						{
							type: 'string',
							min: 6,
							message: '密码长度不能小于6位',
							trigger: 'blur'
						}
					]
				}
			}
		},
		methods: {
			handleSubmit(name) {
				this.$refs[name].validate((valid) => {
					if (valid) {
						this.$Message.success('Success!');
					} else {
						this.$Message.error('Fail!');
					}
				})
			}
		}
	}
</script>

<style scoped="scoped">
	.login-wrapper {
		height: 100%;
		background-color: #515a56;
	}

	.login-header {
		width: 380px;
		margin-top: 50px;
		height: max-content;
	}
</style>
