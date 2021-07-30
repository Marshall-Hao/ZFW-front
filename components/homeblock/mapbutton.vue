<template>
	<view class="mapbutton" @click="showmap">
	</view>
</template>

<script>
	export default {
		name:"mapbutton",
		data() {
			return {
				
			};
		},
		methods: {
			showmap () {
				this.$emit('showmap')
			}
		}
	}
</script>

<style lang="scss">
	.mapbutton {
		height: 90px;
		width: 100%;
		border-radius: 8px;
		background-image: url(https://zfwmp-sh.oss-cn-shanghai.aliyuncs.com/browse/map%20button.svg);
		background-repeat: no-repeat;
		background-size: cover;
	}
</style>
