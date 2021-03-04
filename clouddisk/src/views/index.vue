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
			<div class="top-select d-flex align-items-center" >
				<Checkbox size="small"><span class="ml-2">全选</span></Checkbox>
			</div>
		</div>
		
		<div class="index-list">
			<div v-for="(item,index) in 1000">{{index}}</div>
		</div>
		
		<div class="index-page d-flex align-items-center px-3 border-top">
			 <Page :total="100" show-sizer />
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
		height: 90px;
	}
	.top-search{
		width: 200px;
	}
	.top-button{
		height: 50px;
	}
	.index-page{
		height: 55px;
		position: absolute;
		left: 0;
		bottom: 0;
		right: 0;
	}
	.index-list{
		position: absolute;
		overflow-y: auto;
		left: 0;
		right: 0;
		bottom: 55px;
		top:90px;
	}
	.top-select{
		height: 40px;
	}
</style>
