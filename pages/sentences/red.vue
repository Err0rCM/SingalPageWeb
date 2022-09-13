<template>
			<view class="uni-margin-wrap">
				<swiper class="swiper" circular :indicator-dots="indicatorDots">
					<swiper-item>
						<view class="swiper-item">
							<image src="/static/images/R3/R3_XXJJ_1.png"></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="/static/images/R3/R3_XXJJ_2.png"></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="/static/images/R3/R3_XXJJ_3.png"></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="/static/images/R3/R3_XXJJ_4.png"></image>
						</view>
					</swiper-item>
				</swiper>
			</view>

</template>

<script>
	export default {
		data() {
			return {
				background: ['color1', 'color2', 'color3'],
				indicatorDots: true,
				interval: 2000,
				duration: 500
				
			}
		},
		methods: {
			
			
		}
	}
</script>

<style>
	.uni-margin-wrap {
		 width:690rpx;
		 width: 100%;
		
	}
	.swiper {
		height: 1200upx;
	}
	.swiper-item {
		width: 100%;
		display: block;
		height: 1000upx;
		line-height: 1000upx;
		text-align: center;
	}
	.swiper-item image{
		width: 100%;
		height: 1100upx;
	}
</style>
