<template>
		<view class="tabPageSlider">
			<view>
				<view class="title" align="center">
					信仰的力量
				</view>
			</view>	
			<view class="boxOne">
				<view class="one">
					<video src="/static/images/R5/xl1xydll.mp4" class="boxVideo"></video>
				</view>
			</view>
			<view class="boxTwo">
				评论/留言
				<view id="app" class="boxButton" >
					<form   @submit="formSubmit()" >
						<input class="Left" name="text" type="text" id='textbox' >
						<button form-type="submit" class="Right" @click="on()">提交</button>
					</form>
				
				<!-- <p>{{msg}}</p> -->
				</view>
			</view>
			<view class="five">
				<h6 align=center>没有更多了！</h6>
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
			
			on(){	
				uni.request({
			    url:'http://api.err0r.top:5000/api/ip',
				method:'GET',
				success: (res) => {
	
					console.log(res);
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
				let textcontent = document.getElementsByTagName('input')[0].value;
				// let ips =document.getElementById("text").value;
				// console.log(ips)
				uni.request({
					url: 'http://api.err0r.top:5000/api/comment',
					method:'POST',
					data: {
						ip: user,
						text: textcontent,
						video: "2"
						
					},
					 success:res=>{
					        console.log(res.data);
					        this.carouselData = res.data
							}
				})
				 
			}
			
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
