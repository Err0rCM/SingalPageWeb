<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
			
		</view>
		<text id="text">123</text>
		<button  type="button" @onclick="text()"></button>
	</view>

</template>


<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
			
		},
		onLoad() {

		},
		methods: {
			text(){
				uni.request({
				    url:'http://pv.sohu.com/cityjson?ie=utf-8',
					method:'POST',
					success: (res) => {
				        const reg = /\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}/;
						let ip = reg.exec(res.data);
						document.getElementById("text").innerHTML="ip[0]";
						
					}
				})
			}

	
	}
}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
