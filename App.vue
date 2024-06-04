<script>
	export default {
		onLaunch: function() {
			
			//#ifdef APP-PLUS
			    //获取已保存在本地的用户信息，该内容在登录页面登录成功之后，才保存到本地的
				console.log('App Launch');
			    const userLoginInfo = uni.getStorageSync('userLoginInfo');
			    if (!userLoginInfo) {
			        uni.reLaunch({
			            url: "/pages/User/User",
			            success: () => {
			                //跳转完页面后再关闭启动页
			               plus.navigator.closeSplashscreen();
			            }
			       })
			    } else {
			        plus.navigator.closeSplashscreen(); //关闭启动页，进入首页
			    }
			    //#endif
			
			},
		onShow: function() {
			 setTimeout(() => {
			        // #ifdef APP-PLUS 
			        plus.navigator.closeSplashscreen()
			        // #endif
			    }, 2000)
		},
		onHide: function() {
			console.log('App Hide')
		},
		globalData:{
			
		},  // 全局变量
		methods:{     //全局函数
			
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */
	@import "uview-ui/index.scss";
//	@import "colorui/main.css";
//	@import "colorui/icon.css";
	@import '@/uni_modules/uni-scss/index.scss';
	/* #ifndef APP-NVUE */
	@import '@/static/customicons.css';
	// 设置整个项目的背景色
	

	page {
		background-color: #f5f5f5;
	}

	/* #endif */
	.example-info {
		font-size: 14px;
		color: #333;
		padding: 10px;
	}
</style>
