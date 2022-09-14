<template>
	<view>
		<view class="uni-margin-wrap">
			<swiper class="swiper" circular :indicator-dots="indicatorDots">
				<swiper-item>
					<view class="swiper-item">
						<image src="/static/images/R4/R2-XXSC-01.png"></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="/static/images/R4/R2-XXSC-02.png"></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="/static/images/R4/R2-XXSC-03.png"></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="/static/images/R4/R2-XXSC-04.png"></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
		
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
