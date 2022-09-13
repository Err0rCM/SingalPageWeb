<template>
	<view class="all">
		<view class="con_header">
			<image width="70%" src="../../static/startimage/loc_text.png"></image>
		</view>
		<view class="con_center" :style="{height: deviceheight + 'px'}">
			<!--重温红色印记-->
			<image src="../../static/startimage/1.png" class="imagepos animate-icon-up" style="top: 8%; right: 9%" @click="toPage('1')"></image>
			<!--重温艰苦创业-->
			<image src="../../static/startimage/2.png" class="imagepos animate-icon-up" style="top: 32%; left: 54%"></image>
			<!--加强基层治理-->
			<image src="../../static/startimage/3.png" class="imagepos animate-icon-up" style="top: 12%; right: 2%"></image>
			<!--强生态治理-->
			<image src="../../static/startimage/4.png" class="imagepos animate-icon-up" style="top: 39%; left: 12%"></image>
			<!--数字经济-->
			<image src="../../static/startimage/5.png" class="imagepos animate-icon-up" style="top: 18%; left: 58%"></image>
			<!--两新集群-->
			<image src="../../static/startimage/6.png" class="imagepos animate-icon-up" style="top: 21%; right: 2%"></image>
		</view>
		<view class="con_footer">
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				deviceheight: ''
			}
		},
		onLoad(options){
			let that = this;
			uni.getSystemInfo({
				success: function(res){
					console.log(res.windowWidth);
					console.log(res.windowHeight);
					console.log(res.screenHeight);
					
					const deviceheight = res.windowHeight - 180;
					
					console.log('deviceheight=' + deviceheight);
					
					that.deviceheight = deviceheight;
				}
			});
			
			
		},
		methods: {
			toPage(code){
				uni.switchTab({
					url: "../tab/index/index"
				})
			}
		}
	}
</script>

<style>
	.all{
		position: relative;
	}
	.imagepos{
		position: absolute;
		width: 170upx;
		height: 60upx;
		z-index: 2;
	}
	.con_center{
		width: 100%;
		/* height: 1200upx; */
		position: relative;
		background: url('../../static/startimage/map.png');
		background-size: 100% 100%;
	}
	.con_footer{
		position: absolute;
		right: 0;
		bottom: 36upx;
		width: 560upx;
		height: 272upx;
		background: url('../../static/startimage/loc_mark.png');
		background-size: 100% 100%; 
	}
	@keyframes iconup{
		25%{
			transform: translateY(10px);
		}
		50%,100%{
			transform: translateY(0);
		}
		75%{
			transform: translateY(-10px);
		}
	}
	.animate-icon-up{
		animation: iconup 1.5s linear infinite;
	}
</style>
