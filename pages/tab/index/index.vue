<template>
	<view>
		<view class="tabPageSlider">
			<view class="uni-margin-wrap">
				<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
					<swiper-item>
						<view class="swiper-item">
							<image src="/static/images/R1/R1swiper1.png"></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="/static/images/R1/R1swiper2.png"></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="/static/images/R1/R1swiper3.png"></image>
						</view>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<view class="boxOne">
			<!--学习金句-->
			<view class="oneLeft">
				<image src="/static/images/R1/R1_L1.png" class="boxImage" @click="toRed('1')"></image>
			</view>
			<!--学习视频-->
			<view class="oneRight">
				<image src="/static/images/R1/R1_L2.png" class="boxImage" @click="toRed1('1')"></image>
			</view>
			
			
		</view>
		<view class="boxTwo">
			<!--学习手册-->
			<view class="two">
				<image src="/static/images/R1/R1_L3.png" class="boxImage" @click="toRed2('1')"></image>
			</view>
		</view>
		<view class="boxThree">
			<!--签到打卡-->
			<view class="threeLeft">
				<image src="/static/images/R1/R1Ipx-05.png" class="boxImage" @click="toRed3('1')"></image>
			</view>
			<!--互动功能-->
			<view class="threeRight">
				<image src="/static/images/R1/R1Ipx-06.png" class="boxImage"></image>
			</view>
			
		</view>
		
		<!-- 返回地图页 -->
		<view class="returnMap" @click="returnMap()">返回地图</view>
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
			returnMap() {
				uni.navigateTo({
					url: '../../indexnav/indexnav'
				})
			},
			toRed(code){
				uni.navigateTo({
					url: '../../sentences/red'
				})
				
			},
			toRed1(code){
				uni.navigateTo({
					url: '../../videos/red'
				})
				
			},
			toRed2(code){
				uni.navigateTo({
					url: '../../pamphlets/red'
				})
				
			},
			toRed3(code){
				uni.navigateTo({
					url: '../../sign/red'
				})
				
			}
			// changeIndicatorDots(e) {
			// 	this.indicatorDots = !this.indicatorDots
			// },
			// changeAutoplay(e) {
			// 	this.autoplay = !this.autoplay
			// },
			// intervalChange(e) {
			// 	this.interval = e.detail.value
			// },
			// durationChange(e) {
			// 	this.duration = e.detail.value
			// }
			
		}
	}
</script>

<style>
	.boxImage{
		width: 100%;
		height: 100%;
		border-radius: 15upx;
		
	}
	.returnMap{
		width: 70px;
		height: 70px;
		line-height: 70px;
		background-color: #d75e5e;
		text-align: center;
		border-radius: 50%;
		color: #FFF;
		font-size: 13px;
		position: fixed;
		right: 5px;
		bottom: 50px;
	} 
	.uni-margin-wrap {
		width:690rpx;
		width: 100%;;
	}
	.swiper {
		height: 280upx;
	}
	.swiper-item {
		width: 100%;
		display: block;
		height: 280upx;
		line-height: 280upx;
		text-align: center;
	}
	.swiper-item image{
		width: 100%;
		height: 280upx;
	}
	
	.swiper-list {
		margin-top: 40rpx;
		margin-bottom: 0;
	}
	
	.uni-common-mt{
		margin-top:60rpx;
		position:relative;
	}
	
	.info {
		position: absolute;
		right:20rpx;
	}
	
	.uni-padding-wrap {
	    width:550rpx;
	    padding:0 100rpx;
	}
	.boxOne{
		width: 100%;
		height: 254upx;
		margin: 20upx auto;
		display: flex;
		box-sizing: border-box;
	}
	.oneLeft{
		width: 64%;
		height: 250upx;
		margin: 0 2% auto;
		box-sizing: border-box;
	}
	.oneRight{
		width: 30%;
		height: 250upx;
		box-sizing: border-box;
	}
	
	.boxTwo{
		width: 100%;
		height: 254upx;
		margin: 20upx auto;
		display: flex;
		box-sizing: border-box;
	}
	.two{
		height: 250upx;
		box-sizing: border-box;
		width: 96%; 
		border-radius: 7px;
		margin: 1% 2% auto;
	}
	
	.boxThree{
		width: 100%;
		height: 254upx;
		margin: 20upx auto;
		display: flex;
		box-sizing: border-box;
	}
	.threeLeft{
		width: 46%;
		height: 250upx;
		margin: 2% 2% auto;
		box-sizing: border-box;
	}
	.threeRight{
		width: 46%;
		height: 250upx;
		box-sizing: border-box;
		margin: 2% 2% auto ;
	}
</style>
