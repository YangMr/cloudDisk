<template>
	<Layout class="layout">
		<Header class="bg-white px-0">
			 <Menu @on-select="handleSelect" mode="horizontal" theme="light" :active-name="topActive" class="d-flex align-items-center">
					<div class="layout-logo">企业网盘</div>
			        <MenuItem :name="index" v-for="(item,index) in topMenus" :key="index">
			            <Icon :type="item.icon" />
			            {{item.title}}
			        </MenuItem>
					<div>下拉菜单</div>
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
				topActive : 0,
				topMenus : [
					{
						icon : "ios-paper",
						title : "网盘"
					},
					{
						icon : "ios-people",
						title : "分享"
					},
					{
						icon : "ios-construct",
						title : "更多"
					}
				]
			}
		},
		methods : {
			handleSelect(e){
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
	.footer-left{
		width: 200px;
	}
	.layout-logo{
		width: 200px;
		text-align: center;
		font-size: 25px;
	}
</style>
