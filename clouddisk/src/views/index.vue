<template>
	<div>
		<div class="index-top bg-white border-bottom px-3 ">
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
			<media-list v-for="(item,index) in list" :item="item" :index="index" :key="index"></media-list>
		</div>

		<div class="index-page d-flex align-items-center px-3 border-top">
			<Page :total="100" show-sizer />
		</div>
	</div>
</template>

<script>
	import mediaList from "../components/media-list.vue"
	export default {
		components: {
			mediaList
		},
		data() {
			return {
				list: [{
					type: "dir",
					name: "我的笔记",
					create_time: "2019-12-15 08:00",
					checked: false
				}, {
					type: "dir",
					name: "我的备份",
					create_time: "2019-12-15 08:00",
					checked: false
				}, {
					type: "dir",
					name: "相册管理",
					create_time: "2019-12-15 08:00",
					checked: false
				}, {
					type: "dir",
					name: "我的资源",
					create_time: "2019-12-15 08:00",
					checked: false
				}, {
					type: "image",
					name: "风景.jpg",
					create_time: "2019-12-15 08:00",
					checked: false,
					url: "https://tangzhe123-com.oss-cn-shenzhen.aliyuncs.com/Appstatic/qsbk/demo/datapic/1.jpg"
				}, {
					type: "image",
					name: "海报.jpg",
					create_time: "2019-12-15 08:00",
					checked: false,
					url: "https://tangzhe123-com.oss-cn-shenzhen.aliyuncs.com/Appstatic/qsbk/demo/datapic/2.jpg"
				}, {
					type: "video",
					name: "uniapp实战社区交友教程.mp4",
					create_time: "2019-12-15 08:00",
					checked: false,
					url: "https://douyinzcmcss.oss-cn-shenzhen.aliyuncs.com/%E8%AF%BE%E6%97%B61.%20%E9%A1%B9%E7%9B%AE%E4%BB%8B%E7%BB%8D.mp4"
				}, {
					type: "video",
					name: "uniapp实战商城教程.mp4",
					create_time: "2019-12-15 08:00",
					checked: false,
					url: "https://douyinzcmcss.oss-cn-shenzhen.aliyuncs.com/%E8%AF%BE%E6%97%B61.%20%E9%A1%B9%E7%9B%AE%E4%BB%8B%E7%BB%8D.mp4"
				}, {
					type: "video",
					name: "uniapp实战仿微信教程.mp4",
					create_time: "2019-12-15 08:00",
					checked: false,
					url: "https://douyinzcmcss.oss-cn-shenzhen.aliyuncs.com/%E8%AF%BE%E6%97%B61.%20%E9%A1%B9%E7%9B%AE%E4%BB%8B%E7%BB%8D.mp4"
				}, {
					type: "image",
					name: "摄影.jpg",
					create_time: "2019-12-15 08:00",
					checked: false,
					url: "https://tangzhe123-com.oss-cn-shenzhen.aliyuncs.com/Appstatic/qsbk/demo/datapic/3.jpg"
				}, {
					type: "text",
					name: "记事本.txt",
					create_time: "2019-12-15 08:00",
					checked: false
				}, {
					type: "none",
					name: "压缩包.rar",
					create_time: "2019-12-15 08:00",
					checked: false
				}]
			}
		}
	}
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

	.icon {
		cursor: pointer;
	}
</style>
