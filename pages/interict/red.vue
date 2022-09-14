<template>
		<view class="tabPageSlider">
			<view>
				<view class="title" align="center">
					互动功能
				</view>
			</view>	
		</view>
		
</template>

<script>
	

	export default {
		name: 'app',
		globalData: {
			user: {}
		},
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
	.five{
		line-height: 80px;
	}
</style>
