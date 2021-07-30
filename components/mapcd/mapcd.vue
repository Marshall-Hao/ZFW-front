<template>
	<view>
		<navbar @backtolists="backtolists"></navbar>
		<map style="width: 100%; height: 100vh;"  :markers="covers"></map>
	</view>
</template>

<script>
	export default {
		name:"mapcd",
		data() {
			return {
				
			};
		},
		methods: {
			backtolists() {
				console.log('yeahhh')
				this.$emit('backtolists')
			}
		}
	}
</script>

<style>

</style>
