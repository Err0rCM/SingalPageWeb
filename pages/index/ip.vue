<template>

    <view style="padding:50rpx;">

        <view style="margin-top:60rpx;">
	

            <form @submit="submit">

                <view class="gui-border-b gui-form-item" style="margin-top:80rpx;">

                    <view class="gui-form-body">

                        <input type="number" class="gui-form-input" v-model="driverTel" name="driverTel" placeholder="手机号" placeholder-style="color:#CACED0"/>

                    </view>

                </view>

                 

                <view class="gui-border-b gui-form-item" style="margin-top:30rpx;">

                    <view class="gui-form-body">

                        <input type="password" class="gui-form-input" v-if="isPwd"

                        v-model="password" name="password" placeholder="密码" placeholder-style="color:#CACED0"/>

                        <input type="text" class="gui-form-input" v-if="!isPwd" :disabled="true"

                        v-model="password" name="password" placeholder="密码" placeholder-style="color:#CACED0"/>

                    </view>

                    <text class="gui-form-icon gui-icons gui-text-center"

                        @click="changePwdType" :style="{color:isPwd?'#999999':'#008AFF'}">&#xe609;</text>

                </view>

                 

                <view style="margin-top:50rpx;">

                    <button type="default" class="gui-button gui-bg-blue msgBtn" formType="submit" style="border-radius:50rpx;">

                        <text class="gui-color-white gui-button-text-max">登录</text>

                    </button>

                </view>

            </form>

        </view>

    </view>

</template>

<script>

    uni.request({

        url:  "http://baidu.com/",

        method:'POST',

        header:{'content-type' : "application/x-www-form-urlencoded"},

        data:{

            // 对于上面的form表单提交，我们可以直接在uni.request的data属性中直接提交就行了

			
            driverTel: driverTel,

            password: password

        },

        success: (res) => {

            // 服务器返回结果

        }

    })

</script>