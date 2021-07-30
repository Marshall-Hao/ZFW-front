<template>
	<view class="profileblock">
		<loginblock></loginblock>
	</view>
</template>

<script>
	import loginblock from './loginblock.vue'
	export default {
		components: {
			loginblock
		},
		data() {
			return {
				
			};
		},
	}
</script>

<style lang="scss">
	.profileblock {
		height: 55px;
		width: 100%;
		border-radius: 20px 20px 0 0;
		background-color: #FFFFFF;
	}
</style>
