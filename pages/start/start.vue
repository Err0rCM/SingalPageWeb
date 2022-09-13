<template>
	<view>
		<view class="startView" :style="{ height : iosheight + 'px' }">
			<!-- start -->
			<image class="startImg" :src="imgSrc" mode=""  style="width: 100%; height:100%">
			</image>
			<view class="startENView" @click="toPage()">
				<image class="startEN" src="../../static/startimage/enter.png"></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgSrc: '../../static/startimage/start.jpg',
				iosheight:''
			}
		},
		onLoad() {
			console.log('=hello=');
			let that = this;
			uni.getSystemInfo({
				success:function(res){
					console.log(res.windowWidth);
					console.log(res.windowHeight);
					const ioswidth = res.windowWidth;
					const iosheight = res.windowHeight;
					that.iosheight = iosheight;
					that.imgSrc = '../../static/startimage/startlarge.jpg';
				}
			})
		},
		methods: {
			toPage() {
				uni.navigateTo({
					url: "/pages/indexnav/indexnav"
				});
			}
		}
	}
</script>

<style>
	.startView{
		width: 100%;
		height: 800upx;
	}
	.startENView{
		width: 35%;
		height: 10%;
		z-index: 2;
		position: absolute;
		bottom: 30%;
		right: 32.5%;
	}
	.startENView image{
		width: 100%;
		height: 100%;
	}
	@keyframes shake{
		0%{
			transform: scale(1);
		}
		50%{
			transform: scale(1.1);
		}
		100%{
			transform: scale(1);
		}
	}
	.startEN{
		animation: shake 1s infinite;
	}
</style>
