<template>
	<view>
		<view class="title" align="center">
			  打卡签到
		</view>
		<view>
			<p id="you">one</p>
		</view>
		
		<view>
			<view id="app" class="boxButton" >
				<form   @submit="formSubmit()" >
					<button form-type="submit" class="one" @click="on();getSubmit()">提交</button>
				</form>
			
			<!-- <p>{{msg}}</p> -->
			</view>
			</view>
	</view>
</template>

<script>
	export default {
		globalData: {
			user: {},
			users: {}
		},
		data() {
			return {
				
			}
		},
		methods: {
			on(){
				uni.request({
			    url:'http://pv.sohu.com/cityjson?ie=utf-8',
				method:'POST',
				success: (res) => {
			        const reg = /\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}/;
					let ips = reg.exec(res.data);
					console.log(ips[0]);
					// document.getElementById("text").innerHTML=ips[0];
					getApp().globalData.user = ips[0];
					
				}
			})
			},
			formSubmit(){
				var user = getApp().globalData.user;
						console.log(user);
						// let ips =document.getElementById("text").value;
						// console.log(ips)
						uni.request({
							url: 'http://10.147.17.72:5000/api/Signin',
							method:'POST',
							data: {
								ip: user
							},
							 success:res=>{
									console.log(res.data);
									this.carouselData = res.data
									}
						})
						 
					},
			getSubmit(){
				
				uni.request({
					url: 'http://10.147.17.72:5000/api/getSignInUsers',
					method:'GET',
					 success:res=>{
							console.log(res.data);
							this.carouselData = res.data;
							let json =JSON.toString('result')
							}
				})
				
			}
					
				}
			}
</script>

<style>
	.title{
		height: 80upx;
		margin: 0% 0% auto;
		line-height: 35px;
		background-color: #DD524D;
		color: #FFFFFF;
	}
	
	.one{
		width: 70px;
		height: 70px;
		line-height: 70px;
		background-color: #d75e5e;
		text-align: center;
		border-radius: 50%;
		color: #FFF;
		font-size: 13px;
		position: fixed;
		margin: 0% 45% auto;
		bottom: 50px;
	}
</style>
