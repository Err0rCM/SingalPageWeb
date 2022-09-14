<template>
	<view>
		<view class="title" align="center">
			  打卡签到
		</view>
		<view  class="box" v-for="it in msg">
					<h2 style="width:80%;display:inline-block;white-space: pre-wrap; word-wrap: break-word;height: auto;">ip:{{it.ip}}</h2>
					<br/>
					<h5><text >签到时间：{{it.datetime}}</text></h5>
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
				msg:'你好'
			}
		},
		onShow() {
			this.msg=getApp().globalData.users;4
			this.getSubmit();
		},
		methods: {
			on(){
				uni.request({
			    url:'http://api.err0r.top:5000/api/ip',
				method:'GET',
				success: (res) => {
					var ips =eval(res.data);
					var ip =ips['ip'];
					// document.getElementById("text").innerHTML=ips[0];
					getApp().globalData.user = ip;
					console.log(getApp().globalData.user);
				}
			})
			},
			formSubmit(){
				var user = getApp().globalData.user;
						console.log(user);
						// let ips =document.getElementById("text").value;
						// console.log(ips)
						uni.request({
							url: 'http://api.err0r.top:5000/api/Signin',
							method:'POST',
							data: {
								ip: user
							},
							 success:res=>{
									console.log(res.data);
									this.carouselData = res.data;
									var code =eval(res.data);
									
									if(code['code']==200)
										alert("签到成功！！！");
									else if(code['code']==201)
										alert("今日已签到！！！");
									else
										alert("签到失败！！！");
									}
						})
						 
					},
			getSubmit(){
				
				uni.request({
					url: 'http://api.err0r.top:5000/api/getSignInUsers',
					method:'GET',
					 success:res=>{
							console.log(res.data);
							this.carouselData = res.data;
							var arr =eval(res.data);
							var test =arr.result;
							
							getApp().globalData.users=test;
							this.msg=getApp().globalData.users;
								
							
							
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
	.box{
		width: 100%;
		height: 80upx;
		margin: 1.2% 0% auto;
		display: flex;
		box-sizing: border-box;
		background-color:#F8F8F8;
		color:#DD524D;
	}
</style>
