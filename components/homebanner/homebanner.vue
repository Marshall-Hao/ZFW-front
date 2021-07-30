<template>
	<view class="banner-all">
		<img src="https://zfwmp-sh.oss-cn-shanghai.aliyuncs.com/browse/language-switch-eng%201.svg" :style="{top:statusBarHeight + 'px'}" alt="">
		<swiper :indicator-dots="true"  :duration="1000" class="banner">
			<swiper-item v-for="(item,index) in bannerList" :key="index">
				<image :src="item.url" mode="widthFix"></image>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		name:"home-banner",
		  options: {  
		        styleIsolation: 'shared'  
		  },
		data() {
			return {
				bannerList: [{
					url: '/static/banner1.png'
				}, {
					url: '/static/banner2.png'
				}, {
					url: '/static/banner3.png'
				}],
				statusBarHeight: 20
			};
		},
		created() {
			// get mobile phone data
			const info = uni.getSystemInfoSync();
			this.statusBarHeight = info.statusBarHeight + 8
		}			
	}
</script>

<style lang="scss" >
	.banner-all {
		height: 230px;
		img {
			position: fixed;
			left: 20px;
			height: 20px;
			width: 20px;
			z-index: 5;
		}
		.banner {
			height: 100%;
			/deep/ .wx-swiper-dots { // 指示点整个区域
			        top: 190px!important;
					left: 340px!important;
			    }
			    /deep/ .wx-swiper-dot { // 指示点元素默认样式
			        width: 9rpx!important;
			        height: 9rpx!important;
			        background: #EEEEEE!important;
			    }
			    /deep/ .wx-swiper-dot-active { // 指示点元素激活（当前选中）状态样式
					width: 27rpx!important;
					height: 9rpx!important;
					border-radius: 9rpx!important;
			        background: #EEEEEE!important;
			    }
			image {
				height: 100%;
				width: 100%;
			}
		}
	}
	
</style>
