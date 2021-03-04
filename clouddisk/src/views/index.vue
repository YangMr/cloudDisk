<template>
	<div>
		<div class="index-top bg-white border-bottom px-3">
			<div class="d-flex top-button align-items-center">
				<Button type="primary" icon="ios-search" class="mr-2">上传</Button>
				<Button icon="ios-search" class="mr-2">新建文件夹</Button>
				<Button icon="ios-search" class="mr-2">下载</Button>
				<Button icon="ios-search" class="mr-2">分享</Button>
				<Button icon="ios-search" class="mr-2">重命名</Button>
				<Button icon="ios-search" class="mr-2">删除</Button>
				<Input class="ml-auto top-search" search enter-button placeholder="请输入关键词" />
			</div>
			<div class="top-select d-flex align-items-center">
				<Checkbox size="small"><span class="ml-2">全选</span></Checkbox>
			</div>
		</div>

		<div class="index-list">
			<div class="border-bottom px-3 py-2">
				<Row>
					<Col span="12" class="d-flex align-items-center">
					<Checkbox size="small" class="mb-0 mr-3"></Checkbox>
					<i class="iconfont icon-file-b-2 text-warning mr-3" style="font-size:28px"></i>
					<small>我的目录</small>
					<div class="ml-auto text-primary">
						<Tooltip content="分享" placement="bottom">
							<Icon type="md-share" size="18" class="mx-2 icon" />
						</Tooltip>
						<Tooltip content="下载" placement="bottom">
							<Icon type="md-cloud-download" size="18" class="mx-2 icon" />
						</Tooltip>

						<Dropdown>							
							<Icon type="ios-more" size="18" class="mx-2 icon" />
							<DropdownMenu slot="list">
								<DropdownItem>重命名</DropdownItem>
								<DropdownItem>删除</DropdownItem>
							</DropdownMenu>
						</Dropdown>


					</div>
					</Col>
					<Col span="6" class="d-flex align-items-center">-</Col>
					<Col span="6" class="d-flex align-items-center"><small class="text-secondary">2021-03-04 15:00:01</small></Col>
				</Row>
			</div>
		</div>

		<div class="index-page d-flex align-items-center px-3 border-top">
			<Page :total="100" show-sizer />
		</div>
	</div>
</template>

<script>
</script>

<style scoped="scoped">
	.index-top {
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		height: 90px;
	}

	.top-search {
		width: 200px;
	}

	.top-button {
		height: 50px;
	}

	.index-page {
		height: 55px;
		position: absolute;
		left: 0;
		bottom: 0;
		right: 0;
	}

	.index-list {
		position: absolute;
		overflow-y: auto;
		left: 0;
		right: 0;
		bottom: 55px;
		top: 90px;
	}

	.top-select {
		height: 40px;
	}
	
	.icon{
		cursor: pointer;
	}
</style>
