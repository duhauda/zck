<template>
	<view >
		<view class="" style="margin-left: 38vw;">
	<u-upload
			:fileList="fileList1"
			@afterRead="afterRead"
			@delete="deletePic"
			name="1"
			multiple
			:maxCount="1"
		></u-upload>
		</view>
		<u-picker :show="show" :columns="columns" @cancel='show=false' @confirm='send'></u-picker>
		<u-button @click="show = true">选择性别</u-button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				fileList1: [],
					show: false,
					columns: [
					['女', '男']
				],
				gender:''
			}
		},
		methods: {
			// 删除图片
			deletePic(event) {
			this[`fileList${event.name}`].splice(event.index, 1)
			},
			async afterRead(event) {
							// 当设置 multiple 为 true 时, file 为数组格式，否则为对象格式
							let lists = [].concat(event.file)
							let fileListLen = this[`fileList${event.name}`].length
							lists.map((item) => {
								this[`fileList${event.name}`].push({
									...item
								})
							})
							this.adress=this.fileList1[0].url
						},
			send(e){
				console.log(e);
				this.gender=e.value
				console.log(this.gender);
			}
		}
	}
</script>

<style>

</style>
