<template>
	<view class="container">
		<view class="title">青瑶图床</view>
		<view class="">
			<view class="">请上传图片</view>
			<view>
				<uni-file-picker v-model="imageValue" fileMediatype="image" mode="grid" @success="success" @fail="fail" />
			</view>
		</view>
	</view>
</template>

<script>
const upload = uniCloud.importObject('upload');
export default {
	data() {
		return {
			imageValue: '',
			imgArr: []
		};
	},
	onLoad() {},
	methods: {
		success(e) {
			console.log(e);
			this.imgArr = e.tempFilePaths;
		},
		fail(e) {
			console.log(e);
		}
	}
};
</script>

<style lang="scss" scoped>
.title {
	text-align: center;
	font-size: 60rpx;
}
.uni-file-picker {
	width: 400px;
	height: 400px;
	/deep/ .uni-file-picker__container {
		width: 100%;
		height: 100%;
	}
}
</style>
