<template>
	<view class="navbar">
		<view class="navbar-fixed">	
		<!-- status bar -->
			<view :style="{height:statusBarHeight + 'px'}"></view>
			<!-- navbar content -->
			<view class="navbar-content" :style="{height:navBarHeight + 'px', width:windowWidth + 'px'}">
				<view v-if="!mapshow" class="navtools">
					<img src="https://zfwmp-sh.oss-cn-shanghai.aliyuncs.com/search/search_loupe_orange.svg" alt="">
					<img class="mapicon" src="https://zfwmp-sh.oss-cn-shanghai.aliyuncs.com/browse/map_2.svg" alt="">
					<img class="translateicon" src="https://zfwmp-sh.oss-cn-shanghai.aliyuncs.com/browse/language-switch-eng%201.svg" alt="">
				</view>
				<view v-else class="backdes" @click="backtolists">
					<img class="backlists" src="https://zfwmp-sh.oss-cn-shanghai.aliyuncs.com/browse/restaurantlists%202.svg" mode=""></img>
					<view class="backtext">商家列表</view>
				</view>
			</view>
		</view>
		<view :style="{height: statusBarHeight+navBarHeight+'px'}"></view>
	</view>
</template>

<script>
	export default {
		name:"navbar",
		props: {
			 mapshow: {
			      type: Boolean,
			      default: true
			    }
		},
		data() {
			return {
				statusBarHeight:20,
				navBarHeight: 45,
				windowWidth: 375
			};
		},
		methods: {
			backtolists() {
				console.log('asdasdasd')
				this.$emit('backtolists')
			}
		},
		created() {
				// get mobile phone data
						const info = uni.getSystemInfoSync();
						this.statusBarHeight = info.statusBarHeight
						this.windowWidth = info.windowWidth
						// get the small pill location
						 // #ifndef H5 || APP-PLUS || MP-ALIPAY
						const menuButtoninfo = uni.getMenuButtonBoundingClientRect();
						console.log(menuButtoninfo);
						// (pill bottom height - status bar height) + ( pill top height - status inner height)
						this.navBarHeight = (menuButtoninfo.bottom - info.statusBarHeight) + (menuButtoninfo.top - info.statusBarHeight)
						this.windowWidth = menuButtoninfo.left
						 // #endif
			
		},
	}
</script>

<style lang="scss">
	.navbar{
		.navbar-fixed{
	    width: 100%;
	    position: fixed;
	    top: 0;
	    left: 0;
	    background-color: #FFFFFF;
	    z-index: 99;
			.navbar-content{
			  box-sizing: border-box;
			  display: flex;
			  height: 45px;
			  justify-content: start;
			  align-items: center;
			  padding: 0 15px;
			  
			  .backdes {
				  display: flex;
				  flex-direction: column;
				  align-items: center;
				  img {
					height: 20px;
					width: 20px; 
				  }
				  
				  .backtext {
					 margin-top: 3px;
					 font-size: 8px;
					 font-weight: lighter;
				  }				  
			  }
			  
			  .navtools {
				box-sizing: border-box;
				width:100px;
				display: flex;
				justify-content: space-between;
				
				img {
				  height: 20px;
				  width: 20px;
				}
				.mapicon {
					padding-left: 8px;
					border-left: 1px solid #f3f3f3;
				}	
				.translateicon {
					padding-left: 8px;
					border-left: 1px solid #f3f3f3;
				}
				
			  }
			}
		}
	}
</style>
