<template>
	<view class="reslists">
		<myaddress></myaddress>
		<allres></allres>
	</view>	
</template>

<script>
	import myaddress from './myaddress.vue';
	import allres from './allres.vue'
	export default {
		name:"reslists",
		components: {
			myaddress,
			allres
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style>
	.reslists {
		margin-top: 20px;
	}
</style>
