<template>
	<div>
		<div class="index-top border-bottom d-flex px-3 py-2">
			<Button type="primary" icon="ios-search" class="mr-2">上传</Button>
			<Button icon="ios-search" class="mr-2">新建文件夹</Button>
			<Button icon="ios-search" class="mr-2">下载</Button>
			<Button icon="ios-search" class="mr-2">分享</Button>
			<Button icon="ios-search" class="mr-2">重命名</Button>
			<Button icon="ios-search" class="mr-2">删除</Button>
			<Input class="ml-auto top-search" search enter-button placeholder="请输入关键词" />
		</div>
	</div>
</template>

<script>
</script>

<style scoped="scoped">
	.index-top{
		position: absolute;
		top : 0;
		left: 0;
		right: 0;
	}
	.top-search{
		width: 200px;
	}
</style>
