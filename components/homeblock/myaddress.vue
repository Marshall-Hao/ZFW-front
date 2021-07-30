<template>
	<view class="myaddress">
		<image class="locmark" src="https://zfwmp-sh.oss-cn-shanghai.aliyuncs.com/browse/location_marker1.svg" mode="aspectFill"></image>	
		<view class="realloc">
			<text class="userloc">成都市城市中心</text>
			<image class="arrow" src="https://zfwmp-sh.oss-cn-shanghai.aliyuncs.com/restaurant_show/chevron_big_left.svg" mode="aspectFill"></image>
		</view>
		<text class="locextension">周边的食物保护计划商家</text>
	</view>
</template>

<script>
	
</script>

<style lang="scss">
	.myaddress {
		display: flex;
		align-items: baseline;
		margin-bottom: 12px;
		.locmark {
			height: 16px;
			width: 16px;
			margin-right: 2px;
		}
		.realloc {
			margin-right: 10px;
			border-bottom: 1px solid black;
			.userloc {
				font-weight: bold;
				font-size: 14px;
			}
			.arrow {
				height: 9px;
				width: 9px;
				margin-left:2px;
				transform: rotate(-90deg);
			}	
		}
		.locextension {
			font-size: 12px;
			font-weight: 700;
		}
	}
</style>
