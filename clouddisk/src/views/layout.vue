<template>
	<Layout class="layout">
		<Header class="bg-white px-0">
			<Menu @on-select="handleSelect" mode="horizontal" theme="light" :active-name="topActive" class="d-flex align-items-center">
				<div class="layout-logo">企业网盘</div>
				<MenuItem :name="index" v-for="(item,index) in topMenus" :key="index">
				<Icon :type="item.icon" />
				{{item.title}}
				</MenuItem>
				<div class="ml-auto mr-3">
					<Dropdown style="margin-left: 20px" placement="bottom-end">
						<a href="javascript:void(0)">
							<Avatar src="https://i.loli.net/2017/08/21/599a521472424.jpg" />
							管理员
							<Icon type="ios-arrow-down"></Icon>
						</a>
						<DropdownMenu slot="list">
							<DropdownItem>个人资料</DropdownItem>
							<DropdownItem>修改密码</DropdownItem>
							<DropdownItem>安全退出</DropdownItem>
						</DropdownMenu>
					</Dropdown>
				</div>
			</Menu>
		</Header>
		<Layout>
			<Sider hide-trigger class="bg-light">侧边栏</Sider>
			<Content class="bg-white">主内容</Content>
		</Layout>
		<Footer class="bg-white d-flex p-0 ">
			<div class="bg-light footer-left">
				空间容量信息
			</div>
			<div>分页</div>
		</Footer>
	</Layout>
</template>

<script>
	export default {
		data() {
			return {
				topActive: 0,
				topMenus: [{
						icon: "ios-paper",
						title: "网盘"
					},
					{
						icon: "ios-people",
						title: "分享"
					},
					{
						icon: "ios-construct",
						title: "更多"
					}
				]
			}
		},
		methods: {
			handleSelect(e) {
				console.log(e)
				this.topActive = e;
			}
		}
	}
</script>

<style scoped="scoped">
	.layout {
		height: 100%;
	}

	.footer-left {
		width: 200px;
	}

	.layout-logo {
		width: 200px;
		text-align: center;
		font-size: 25px;
	}
</style>
