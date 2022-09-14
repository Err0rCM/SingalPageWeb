<template>
	<view>
		<view class="title">
			<h2 align="center">用户IP：{{msg}}</h2>
		</view>
		<view class="box" @click="toRed1('1')">
			<h3>我的参观证书</h3>
		</view>
		<view class="box" @click="toRed2('2')">
			<h3>今日签到</h3>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				msg:"登录"
				
			}
		},
		globalData: {
			user: {}
		},
		onShow() {
			this.msg=getApp().globalData.user;
			this.on();
		},
		methods: {
			on(){
				uni.request({
			    url:'http://api.err0r.top:5000/api/ip',
				method:'GET',
				success: (res) => {
				
					console.log(res.data);
					var ips =eval(res.data);
					var ip =ips['ip'];
					getApp().globalData.user = ip;
					this.msg=getApp().globalData.user;
				}
			})
			},
			toRed1(code){
				uni.navigateTo({
					url: '../../interict/red'
				})	
			},
			toRed2(code){
				uni.navigateTo({
					url: '../../sign/red'
				})
			}
		}
	}
</script>

<style>
	.title{
		height: 80upx;
		margin: 3% 0% auto;
		line-height: 35px;
		background-color: #DD524D;
		color: #FFFFFF;
	}
	.box{
		width: 100%;
		height: 70upx;
		margin: 10upx auto;
		display: flex;
		box-sizing: border-box;
		background-color: #E3E3E3;
	}
</style>
