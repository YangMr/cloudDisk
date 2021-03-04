<template>
	<Layout class="layout">
		<Header class="bg-white px-0 layout-header">
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
			<Sider hide-trigger class="sider">
				<Menu @on-select="handleSiderSelect" class="sider-menu" theme="light" active-name="1" width="200px">
				        <MenuGroup title="全部文件">
				            <MenuItem name="1">
				                <Icon type="md-document" />
				                图片
				            </MenuItem>
				            <MenuItem name="2">
				                <Icon type="md-chatbubbles" />
				                视频
				            </MenuItem>
							<MenuItem name="3">
							    <Icon type="md-chatbubbles" />
							    音乐
							</MenuItem>
							<MenuItem name="4">
							    <Icon type="md-chatbubbles" />
							    其他
							</MenuItem>
				        </MenuGroup>
				        <MenuGroup title="其他操作">
				            <MenuItem name="5">
				                <Icon type="md-heart" />
				                我的分享
				            </MenuItem>
				            <MenuItem name="6">
				                <Icon type="md-leaf" />
				                回收站
				            </MenuItem>
				        </MenuGroup>
				    </Menu>
			</Sider>
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
			},
			handleSiderSelect(e){
				console.log(e)
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
	.layout-header{
		height: 60px;
		line-height: 60px;
	}
	.sider,.sider-menu{
		background-color: #ebf0f1;
	}
</style>
