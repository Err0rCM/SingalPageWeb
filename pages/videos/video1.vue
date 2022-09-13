<template>
		<view class="tabPageSlider">
			<view>
				<view class="title" align="center">
					半只梨的故事
				</view>
			</view>	
			<view class="boxOne">
				<view class="one">
					<video src="/static/images/R5/xl1bzl.mp4" class="boxVideo"></video>
				</view>
			</view>
			<view class="boxTwo">
				评论/留言
				<view id="app" class="boxButton">
					<form action=" " method="POST">
						<input class="Left" type="text" >
						<button class="Right" type="primary">Button</button>
					</form>
				
				<!-- <p>{{msg}}</p> -->
				</view>
			</view>
			<p align="center">没有更多了</p>
		</view>
		
</template>

<script>

	export default {
		name: 'app',
		data() {
			return {
				 msg: ''
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.boxVideo{
		width: 100%;
		height: 500upx;
		border-radius: 15upx;
	}
	.title{
		height: 80upx;
		margin: 0% 0% auto;
		line-height: 35px;
		background-color:#DD524D;
		color: #FFFFFF;
	}
	.boxOne{
		width: 100%;
		height: 254upx;
		margin: 20upx auto;
		display: flex;
		box-sizing: border-box;
	}
	.boxTwo{
		width: 100%;
		height: 210upx;
		margin: 50% 0% auto;
		display: flex;
		box-sizing: border-box;
		background-color:#e3e3e3;
		color:#DD524D;
	}
	.boxButton{
		width: 65%;
		height: 100upx;
		margin: 0% 5% auto;
		box-sizing: border-box;
		
	}
	.one{
		height: 1000upx;
		box-sizing: border-box;
		width: 96%; 
		border-radius: 7px;
		margin: 3% 2% auto;
	}
	.Left{
		width: 80%;
		height: 100upx;
		margin: 15% -19% auto;
		box-sizing: border-box;
		background-color:#FFFFFF;
		
	}
	.Right{
		width: 35%;
		height: 100upx;
		margin: -20.5% 63% auto;
		box-sizing: border-box;
	}
	
</style>
