<template>
	<view>
		<view class="tabPageSlider">
			<view class="boxOne">
				<!--半只梨的故事-->
				<view class="one">
					<image src="/static/images/R5/20220526084833bzl.jpg" class="boxImage" @click="toRed1('1')" ></image>
				</view>
			</view>
			<view>
				<view class="three">
					半只梨的故事
				</view>
			</view>
			<view class="boxTwo">
				<!--信仰的力量-->
				<view class="two">
					<image src="/static/images/R5/20220526084918xydll.jpg" class="boxImage" @click="toRed2('1')"></image>
				</view>
			</view>
			<view>
				<view class="four">
					信仰的力量
				</view>
			</view>
			<view>
				<view class="five">
					<h6 align=center>没有更多了！</h6>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: ['color1', 'color2', 'color3'],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		methods: {
			toRed1(code){
				uni.navigateTo({
					url: 'video1'
				})
				
			},
			toRed2(code){
				uni.navigateTo({
					url: 'video2'
				})
				
			},
		}
	}
</script>

<style>
	.boxImage{
		width: 100%;
		height: 400upx;
		border-radius: 15upx;
	}
	.one{
		height: 1000upx;
		box-sizing: border-box;
		width: 96%; 
		border-radius: 7px;
		margin: 1% 2% auto;
	}
	.two{
		height: 250upx;
		box-sizing: border-box;
		width: 96%; 
		border-radius: 7px;
		margin: 2% 2% auto;
	}
	.three{
		height: 100upx;
		margin: 20% 2% auto;
		line-height: 50px;
		background-color:#F1F1F1;
	}
	.four{
		height: 100upx;
		margin: 21% 2% auto;
		line-height: 50px;
		background-color:#F1F1F1;
	}
	.five{
		line-height: 80px;
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
		height: 254upx;
		margin: 20upx auto;
		display: flex;
		box-sizing: border-box;
	}
	
	
	
	    
</style>
